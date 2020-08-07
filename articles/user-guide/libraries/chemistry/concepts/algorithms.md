---
title: 模擬 Hamiltonian Dynamics
description: 瞭解如何使用 Trotter-Plat'home co. 公式和 qubitization 來處理 Hamiltonian 模擬。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 40f79a66ae95e20a8b1c19af735eedca5e3c15ef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869523"
---
# <a name="simulating-hamiltonian-dynamics"></a>模擬 Hamiltonian Dynamics

一旦將 Hamiltonian 表示為基本運算子的總和，就可以使用已知的技術主機，將 dynamics 編譯成基本閘道作業。
有三種有效率的方法，包括 Trotter – Plat'home co. 公式、unitaries 和 qubitization 的線性組合。
我們將在下面說明這三種方法，並提供 Q# 如何使用 Hamiltonian 模擬程式庫來執行這些方法的具體範例。


## <a name="trottersuzuki-formulas"></a>Trotter – Plat'home co. 公式
Trotter-Plat'home co. 公式背後的概念很簡單：將 Hamiltonian 表達為容易模擬 Hamiltonians 的總和，然後將總進化數估計為這些較簡單演變的一系列。
特別是，let $H = \ sum_ {j = 1} ^ m H_j $ 是 Hamiltonian。
然後，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2) ，$ $，也就是說，如果 $t \ll $1，則此近似值中的錯誤會變成可忽略的。
請注意，如果 $e ^ {-i H t} $ 是普通指數，則此近似值中的錯誤不會 $O (m ^ 2 t ^ 2) $：它會是零。
之所以會發生此錯誤，是因為 $e ^ {-iHt} $ 是運算子指數，因此使用此公式時發生錯誤，因為 $H _j $ 詞彙未向下 (，*亦即*$H _j H_k \ne H_k H_j $ 一般) 。

如果 $t $ 很大，則 Trotter – Plat'home co. 公式仍然可以藉由將其細分為一系列簡短的時間步驟，來正確模擬 dynamics。
讓 $r $ 成為在時間演進期間所採取的步驟數，因此每次執行步驟時，$t/r $。 然後，我們有 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left ( \ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r) ，$ $，這表示如果 $r $ 縮放為 $m ^ 2 t ^ 2/\ epsilon $，則最多可為任何 $ \epsilon>$0 的 $ \epsilon $ 建立錯誤。

藉由建立一連串的運算子指數來建立更精確的近似值，使錯誤詞彙取消。
最簡單的這類公式，第二個 order Trotter-Plat'home co. 公式，採用的格式為 $ $ U_2 (t) = \left ( \ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2) $ $ 可以針對任何 $ \epsilon>$0，選擇將 $r $ 調整為 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $，以小於 $ \epsilon $ 的錯誤。

更高順序的公式（特別是 ($ 2k $) 第一個 $k>$0 的順序）可以用遞迴方式進行結構化： $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t) ] ^ 2 U_ {2k-2} ( [1-4s_k] t) [U_ {2k-2} (s_k \~ t) ] ^ 2 = e ^ {-iHt} + O ( # B11 m t) ^ {2k + 1}/r ^ {2k} ) ，$ $，其中 $s _k = (4-4 ^ {1/ (2k-1) } ) ^ {-1} $。

最簡單的方式是下列第四個訂單 ($k = $2) 公式，最初是由 Plat'home co. 所引進： $ $ U_4 (t) = [U_2 (s_2 \~ t) ] ^ 2 U_2 ( [1-4s_2] t) [U_2 (s_2 \~ t) ] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4) ，$ $ where $s _2 = (4-4 ^ {1/3} ) ^ {-1} $。
一般來說，任意高階的公式都可以類似地進行結構化;不過，使用較複雜的整合者所產生的成本，通常比大部分實際問題的第四個順序還多。

為了讓上述策略正常執行，我們需要有一個方法可模擬 $e ^ {-iH_j t} $ 的寬類別。
最簡單的 Hamiltonians 系列，而且最有用的是，我們可以在這裡使用 Pauli 運算子。
您可以輕鬆地模擬 Pauli 運算子，因為它們可以使用 Clifford 作業來 diagonalized， (是) 的量子計算中的標準閘道。
此外，一旦 diagonalized，就可以藉由計算其作用所在 qubits 的同位來找到其特徵值。

例如，$ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H) ，$ $，其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0\\\
        0 & e ^ {i t} & 0 & 0\\\
        0 & 0 & e ^ {it} & 0\\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}。
$ $ 這裡，$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ 和 $e ^ {-iHt} \ket {01} = e ^ {-it} \ket {01} $，這是因為 $0 $ 的同位檢查是 $0 $，而位字串 $1 $ 為 $1 $ 的同位檢查。

Pauli 運算子的指數可以直接在中使用作業來執行 Q# <xref:microsoft.quantum.intrinsic.exp> ：
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

針對 Fermionic Hamiltonians，[[約旦– Wigner] 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)可方便地將 Hamiltonian 對應到 Pauli 運算子的總和。
這表示您可以輕鬆地調整上述方法來模擬化學。
以下是在化學中執行這類模擬的簡單範例，而不是手動迴圈 Wigner 標記法中的所有 Pauli 詞彙。
我們的起點是 Fermionic Hamiltonian 的[約旦– Wigner 編碼](xref:microsoft.quantum.chemistry.concepts.jordanwigner)，以程式碼表示為類別的實例 `JordanWignerEncoding` 。

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

模擬演算法可取用的這種 Wigner 標記法格式 Q# 是使用者定義的類型 `JordanWignerEncodingData` 。
在中 Q# ，此格式會傳遞至便利 `TrotterStepOracle` 函式，該函數會使用 Trotter （plat'home co. 整合器）（除了執行所需的其他參數）來傳回運算子將逼近時間演進。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，這項實作為在[模擬使用量子電腦 Hamiltonians 的電子結構](https://arxiv.org/abs/1001.3855)時所討論的一些優化，並[改善量子化學](https://arxiv.org/abs/1403.1539)的配量演算法，以將所需的單一 qubit 旋轉數目降至最低，以及減少模擬錯誤。

## <a name="qubitization"></a>Qubitization

Qubitization 是模擬的替代方法，它會使用來自量子的想法來模擬配量 dynamics。
雖然 qubitization 需要比 Trotter 公式更多的 qubits，但是方法會透過進化時間和容錯來提供最佳的調整。
基於這些理由，它已成為一般模擬 Hamiltonian dynamics 的一種方法，特別是為了解決電子結構問題。

概括而言，qubitization 會透過下列步驟來完成這項工作。
首先，讓 $H = \ sum_j h_j H_j $ 適用于單一和 Hermitian $H _j $ 和 $h _j \ge $0。
藉由執行一對反射，qubitization 會實作用相當於 $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1) }，$ $ （其中 $ | h | _1 = \ sum_j | h_j | $）的運算子。
下一個步驟包括將行走運算子的特徵值從 $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1) } $ 中轉換，其中 $E _k $ 是 $H $ to $e ^ {-iE_k t} $ 的特徵值。
這可以使用各種量子單數值轉換方法來達成，包括[量子信號處理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)。

或者，如果只需要靜態數量 (例如) Hamiltonian 的基礎狀態能源，則會後綴，將[階段估計](xref:microsoft.quantum.libraries.characterization)直接套用到 $W $，藉由採用結果的余弦值來估計結果中的地面狀態能源。
這很重要，因為它允許 spectral 轉換執行傳統方式，而不是使用量子單數值轉換方法。

在更詳細的層級上，qubitization 的執行需要兩個可提供 Hamiltonian 介面的副程式。
不同于 Trotter – Plat'home co. 方法，這些副程式不是傳統的量子，而且其執行方式必須使用 logarithmically 比 Trotter 型模擬所需的 qubits 還多。

Qubitization 使用的第一個量子副程式稱為 $ \operatorname{Select} $，其承諾是產生 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每個 $H _j $ 會假設為 Hermitian 和單一。
雖然這看似嚴格，但請記得 Pauli 的運算子是 Hermitian 和單一的，因此量子化學模擬這類應用程式自然會落入此架構中。
$ \Operatorname{Select} $ 作業（或許很驚訝）實際上是反映作業。
這種情況可以看出，$ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $，因為每個 $H _j $ 是單一和 Hermitian，因此具有特徵值 $ \pm $1。

第二個子程式稱為 $ \operatorname{Prepare} $。
雖然選取作業提供 coherently 存取每個 Hamiltonian 詞彙的方法 $H _j $ 「準備」副程式提供了存取係數 $h _j $、\begin{equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}。
\end{equation} 接著，藉由使用 [乘以控制的階段] 閘道，我們會看到 $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{if} x = 0\\\
        \ket{x} & \text{otherwise} \end{cases}。
$$

$ \Operatorname{Prepare} $ 作業不會直接在 qubitization 中使用，而是用來執行有關狀態的反映，$ \operatorname{Prepare} $ 會建立 $ $ \begin{align} R &amp; = 1-2 \ 運算子名稱 {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} 。
\end{align} $ $

您可以使用 $ \operatorname{Select} $ 和 $R $ 作業，以 $ $ W = \operatorname{Select} R，$ $ 的角度來表示「)  (執行 $W 運算子」，這會再次顯示為等於 $e ^ {\pm i \cos ^ {-1} (H/| H | _1) } $。

這些副程式在中很容易設定 Q# 。
例如，假設有一個簡單的 qubit 橫向 Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。
在此情況下，會叫用 Q# 執行 $ \operatorname{Select} $ 作業的程式碼 <xref:microsoft.quantum.canon.multiplexoperations> ，而 $ \operatorname{Prepare} $ 作業則可使用來執行 <xref:microsoft.quantum.preparation.preparearbitrarystate> 。
如需模擬 Hubbard 模型的範例，請參閱[ Q# 範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)。

針對任意化學問題手動指定這些步驟需要耗費大量的工作，這是使用化學程式庫來避免的。
類似于上述的 Trotter – Plat'home co. 模擬演算法， `JordanWignerEncodingData` 會傳遞至方便的函式，該函數會傳回 `QubitizationOracle` 逐步執行運算子，以及其執行所需的其他參數。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，此執行 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> 適用于指定為 Pauli 字串線性組合的任意 Hamiltonians。
使用來叫用針對化學模擬優化的版本 <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> 。
這個版本經過優化，可將使用在配量線路中以編碼電子 Spectra 所討論的技術降到最低的 T 閘道數目[，並加上線性 T 複雜度](https://arxiv.org/abs/1805.03662)。
