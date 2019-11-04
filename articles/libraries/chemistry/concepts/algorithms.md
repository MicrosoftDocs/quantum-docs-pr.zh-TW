---
title: 模擬 Hamiltonian Dynamics |Microsoft Docs
description: 模擬 Hamiltonian Dynamics 概念檔
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184061"
---
# <a name="simulating-hamiltonian-dynamics"></a>模擬 Hamiltonian Dynamics

一旦將 Hamiltonian 表示為基本運算子的總和，就可以使用已知的技術主機，將 dynamics 編譯成基本閘道作業。
有三種有效率的方法，包括 Trotter – Plat'home co. 公式、unitaries 和 qubitization 的線性組合。
我們將在下面說明這三種方法，並提供具體的 Q # 範例，示範如何使用 Hamiltonian 模擬程式庫來執行這些方法。


## <a name="trottersuzuki-formulas"></a>Trotter – Plat'home co. 公式
Trotter-Plat'home co. 公式背後的概念很簡單：將 Hamiltonian 表達為容易模擬 Hamiltonians 的總和，然後將總進化數估計為這些較簡單演變的一系列。
特別是，let $H = \ sum_ {j = 1} ^ m H_j $ 是 Hamiltonian。
然後，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O （m ^ 2 t ^ 2），$ $，也就是說，如果 $t \ll $1，則此近似值中的錯誤會變成可忽略的。
請注意，如果 $e ^ {-i H t} $ 是普通指數，則此近似值中的錯誤不會 $O （m ^ 2 t ^ 2） $：它會是零。
之所以會發生此錯誤，是因為 $e ^ {-iHt} $ 是運算子指數，因此使用此公式時發生錯誤，因為 $H _j $ 詞彙不會向下計算（*亦即*$H _j H_k \ne H_k H_j $ 一般）。

如果 $t $ 很大，則 Trotter – Plat'home co. 公式仍然可以藉由將其細分為一系列簡短的時間步驟，來正確模擬 dynamics。
讓 $r $ 成為時間演進所採取的步驟數目。
然後，我們有 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left （\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right） ^ r + O （m ^ 2 t ^ 2/r），$ $，表示如果 $r $ 縮放為 $m ^ 2 t ^ 2/\ epsilon $，則任何 $ \epsilon 最多可以為 $ \epsilon $ 建立錯誤> 0 $。

藉由建立一連串的運算子指數來建立更精確的近似值，使錯誤詞彙取消。
最簡單的這類公式（對稱 Trotter 公式或 Strang 分割）採用的格式為 $ $ U_1 （t） = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O （m ^ 3 t ^ 3），藉由選擇 $，可以針對任何 $ \epsilon > 0 $ 建立小於 $ \epsilon $ 的 $ $r $ 可調整為 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $。

更高順序的 Trotter 公式可以根據 $U 的 _1 $ 來加以建造。
最簡單的是下列第四個訂單公式。原本是由 Plat'home co.： $ $ U_2 （t） = U_1 ^ 2 （s_1t） U_1 （[1-4s_1] t） U_1 ^ 2 （s_1 t） = e ^ {-iHt} + O （m ^ 5t ^ 5），$ $ where $s _1 = （4-4 ^ {1/3}） ^{-1}$。
一般來說，任意高階的公式都可以類似地進行結構化;不過，使用較複雜的整合者所產生的成本，通常比大部分實際問題的第四個順序還多。

為了讓上述策略正常執行，我們需要有一個方法可模擬 $e ^ {-iH_j t} $ 的寬類別。
最簡單的 Hamiltonians 系列，而且最有用的是，我們可以在這裡使用 Pauli 運算子。
Pauli 運算子可以輕鬆模擬，因為它們可以使用 Clifford 作業來 diagonalized （在量子運算中是標準閘道）。
此外，一旦 diagonalized，就可以藉由計算其作用所在 qubits 的同位來找到其特徵值。

例如，$ $ e ^ {-iX\otimes X t} = （H\otimes H） e ^ {-iZ\otimes Z t} （H\otimes H），$ $，其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}。
$ $ 這裡，$e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ 和 $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$，這可以直接看到，這是因為 $0 $ 為 $0 $ 的同位，而 bit 字串 $1 $ 是 $1 $ 的相同情況。

您可以使用 <xref:microsoft.quantum.primitive.exp> 作業，直接在 Q # 中執行 Pauli 運算子的指數：
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

針對 Fermionic Hamiltonians，[[約旦– Wigner] 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)可方便地將 Hamiltonian 對應到 Pauli 運算子的總和。
這表示您可以輕鬆地調整上述方法來模擬化學。
以下是在化學中執行這類模擬的簡單範例，而不是手動迴圈 Wigner 標記法中的所有 Pauli 詞彙。
我們的起點是 Fermionic Hamiltonian 的[約旦– Wigner 編碼](xref:microsoft.quantum.chemistry.concepts.jordanwigner)，以程式碼表示，做為 `JordanWignerEncoding` 類別的實例。

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

此格式的 Wigner reprsentation 由 Q # 模擬演算法取用，是使用者定義的型別，`JordanWignerEncodingData`。
在 Q # 中，這種格式會傳遞至便利的函式 `TrotterStepOracle` 會使用 Trotter （Plat'home co. 整合器）（除了執行所需的其他參數），傳回將逼近時間演進的運算子。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，這項實行會套用一些優化，以[模擬使用量子電腦 Hamiltonians 的電子結構](https://arxiv.org/abs/1001.3855)，並[改善量子化學](https://arxiv.org/abs/1403.1539)的配量演算法，以將需要單一 qubit 旋轉，以及減少模擬錯誤。

## <a name="qubitization"></a>Qubitization

Qubitization 是模擬的替代方法，它會使用來自量子的想法來模擬配量 dynamics。
雖然 qubitization 需要比 Trotter 公式更多的 qubits，但是方法會透過進化時間和容錯來提供最佳的調整。
基於這些理由，它已成為一般模擬 Hamiltonian dynamics 的一種方法，特別是為了解決電子結構問題。

概括而言，qubitization 會透過下列步驟來完成這項工作。
首先，讓 $H = \ sum_j h_j H_j $ 適用于單一和 Hermitian $H _j $ 和 $h _j \ge $0。
藉由執行一對反射，qubitization 會實作用等於 $ $W = e ^ {\pm i \cos ^{-1}（H/| h | _1）}，$ $ where $ | h | _1 = \ sum_j | h_j | $ 的運算子。
下一個步驟牽涉到從 $e ^ {i\pm \cos ^{-1}（E_k/| h | _1）} $ 中轉換「行走」運算子的特徵值，其中 $E _k $ 是 $H $ to $e ^ {-iE_k t} $ 的特徵值。
這可以使用各種量子單數值轉換方法來達成，包括[量子信號處理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)。

或者，如果只想要使用靜態數量（例如 Hamiltonian 的基礎狀態能源），則它會後綴將[階段估計](xref:microsoft.quantum.libraries.characterization)直接套用到 $W $，藉由採用結果的余弦值來估計結果中的地面狀態能源。
這很重要，因為它允許 spectral 轉換執行傳統方式，而不是使用量子單數值轉換方法。

在更詳細的層級上，qubitization 的執行需要兩個可提供 Hamiltonian 介面的副程式。
不同于 Trotter – Plat'home co. 方法，這些副程式不是傳統的量子，而且其執行方式必須使用 logarithmically 比 Trotter 型模擬所需的 qubits 還多。

Qubitization 使用的第一個量子副程式稱為 $ \operatorname{Select} $，其承諾是產生 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每個 $H _j $ 都假設為 Hermitian和單一。
雖然這看似嚴格，但請記得 Pauli 的運算子是 Hermitian 和單一的，因此量子化學模擬這類應用程式自然會落入此架構中。
$ \Operatorname{Select} $ 作業（或許很驚訝）實際上是反映作業。
這種情況可以看出，$ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $，因為每個 $H _j $ 是單一和 Hermitian，因此具有特徵值 $ \pm $1。

第二個子程式稱為 $ \operatorname{Prepare} $。
雖然選取作業提供 coherently 存取每個 Hamiltonian 詞彙的方法 $H _j $ 「準備」副程式提供了存取係數 $h _j $、\begin{equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| h | _1}} \ket{j}。
\end{equation} 接著，藉由使用「乘以控制階段」閘道，我們會看到 $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \text{if} x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}。
$$

$ \Operatorname{Prepare} $ 作業不會直接在 qubitization 中使用，而是用來執行有關狀態的反映，$ \operatorname{Prepare} $ 會建立 $ $ \begin{align} R &amp; = 1-2 \ 運算子名稱 {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}。
\end{align} $ $

您可以使用 $ \operatorname{Select} $ 和 $R $ 作業以 $ $ W = \operatorname{Select} R，$ $ 的角度來表示執行運算子（$W $），這可以再次看到，以實作為 $e ^ {\pm i \cos ^{-1}（H/| H | _1）} $ 的運算子。

這些副程式在 Q # 中很容易設定。
例如，假設有一個簡單的 qubit 橫向 Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。
在此情況下，會由 <xref:microsoft.quantum.canon.multiplexoperations>叫用執行 $ \operatorname{Select} $ 作業的 Q # 程式碼，而 $ \operatorname{Prepare} $ 作業則可以使用 <xref:microsoft.quantum.preparation.preparearbitrarystate>來執行。
如需模擬 Hubbard 模型的範例，請參閱[Q # 範例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation)。

針對任意化學問題手動指定這些步驟需要耗費大量的工作，這是使用化學程式庫來避免的。
類似于上述的 Trotter – Plat'home co. 模擬演算法，`JordanWignerEncodingData` 會傳遞至方便函式 `QubitizationOracle`，除了執行所需的其他參數之外，也會傳回逐步解說運算子。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，執行 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> 適用于指定為 Pauli 字串線性組合的任意 Hamiltonians。
使用 <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>叫用針對化學模擬優化的版本。
這個版本經過優化，可將使用在配量線路中以編碼電子 Spectra 所討論的技術降到最低的 T 閘道數目[，並加上線性 T 複雜度](https://arxiv.org/abs/1805.03662)。
