---
title: 模擬 Hamiltonian Dynamics
description: 瞭解如何使用 Trotter-Suzuki 公式和量子位化來處理 Hamiltonian 模擬。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeaa13b99ab07ce22f8a3306a756bf7ac7cde65b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857603"
---
# <a name="simulating-hamiltonian-dynamics"></a>模擬 Hamiltonian Dynamics

一旦將 Hamiltonian 表示為基本運算子的總和後，就可以使用已知技術的主機，將 dynamics 編譯成基本閘道作業。
有三種有效率的方法，包括 Trotter – Suzuki 公式、unitaries 的線性組合和量子位化。
我們將在下面說明這三種方法，並提供 Q# 如何使用 Hamiltonian 模擬程式庫來執行這些方法的具體範例。


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki 公式
Trotter-Suzuki 公式背後的構想很簡單：以簡單的方式來表達 Hamiltonian，以簡化 Hamiltonian，然後將總演進大約視為這些更簡單演進的順序。
尤其是，讓 $H = \ sum_ {j = 1} ^ m H_j $ Hamiltonian。
然後，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2) ，$ $，這表示如果 $t \ll $1，則此近似值中的錯誤會變成可忽略。
請注意，如果 $e ^ {-i H t} $ 是一般的指數，則此近似值中的錯誤不會 $O (m ^ 2 t ^ 2) $：它會是零。
發生此錯誤的原因是 $e ^ {-iHt} $ 是運算子指數，因此使用此公式時發生錯誤，因為 $H _j $ 詞彙不會在 (， *例如*$H _j H_k \ne H_k H_j $ 一般) 。

如果 $t $ 是大型的，Trotter – Suzuki 公式仍然可以用來將動態模擬為一系列簡短的步驟來精確地模擬。
讓 $r $ 成為在時間演進中所採取的步驟數目，因此每次步驟都是針對時間 $t/r $ 執行。 接著，我們有了 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left ( \ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r) $ $ 表示如果 $r $ 調整為 $m ^ 2 t ^ 2/\ epsilon $，則在任何 $ \epsilon>$0 中最多可以有 $ \epsilon $ 的錯誤。

您可以藉由建立一連串運算子指數來建立更精確的近似值，以取消錯誤詞彙。
最簡單的這類公式，第二個順序 Trotter-Suzuki 公式，採用 "$ U_2 (t) = \left ( \ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2) $ $ $r $ 以 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $ 進行調整，可針對任何 $ \epsilon>$0 建立小於 $ \epsilon $ 的錯誤。

甚至更高順序的公式（特別是 ($ 2k $) $k>$0 的第一個順序）可以用遞迴方式進行： $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t) ] ^ 2 U_ {2k-2} ( [1-4s_k] t) [U_ {2k-2} (s_k \~ t) ] ^ 2 = e ^ {-iHt} + O ( # B11 m t) ^ {2k + 1}/r ^ {2k} ) ，$ $，其中 $s _k = (4-4 ^ {1/ (2k-1) } ) ^ {-1} $。

最簡單的是下列第四個順序 ($k = $2) 公式，最初是由 Suzuki 所引進： $ $ U_4 (t) = [U_2 (s_2 \~ t) ] ^ 2 U_2 ( [1-4s_2] t) [U_2 (s_2 \~ t) ] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4) ，$ $，其中 $s _2 = (4-4 ^ {1/3} ) ^ {-1} $。
一般情況下，任意高序位的公式都可以用同樣的方式進行結構化;不過，使用較複雜的整合者所產生的成本，通常會比大部分實際問題的第四個程式的優點更高。

為了讓上述策略正常運作，我們需要有方法來模擬 $e ^ {-iH_j t} $ 的廣泛類別。
我們可以在這裡使用的最簡單 Hamiltonian 系列是 Pauli 操作員。
您可以輕鬆地模擬 Pauli 運算子，因為它們可以使用 Clifford 作業來 diagonalized， (是量子運算) 的標準閘道。
此外，一旦 diagonalized 之後，就可以藉由計算其作用所在量子位的同位來找到其特徵值。

例如，$ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H) ，$ $，其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}。
$ $ 這裡、$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ 和 $e ^ {-iHt} \ket {01} = e ^ {-it} \ket {01} $，這可能是因為 $0 $ 的同位檢查是 $0 $，而位字串 $1 $ 的同位檢查為 $1 $ 的結果。

Pauli 運算子的指數可以使用作業直接實作為 Q# <xref:Microsoft.Quantum.Intrinsic.Exp> ：
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

針對 Fermionic Hamiltonian， [約旦– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner) 可方便地將 Hamiltonian 對應到 Pauli 運算子的總和。
這表示您可以輕鬆地調整上述方法來模擬化學。
以下是在化學中執行這類模擬的簡單範例，而不是在 Jordan-Wigner 標記法中手動迴圈執行。
我們的起點是 Fermionic Hamiltonian 的 [約旦 Wigner 編碼](xref:microsoft.quantum.chemistry.concepts.jordanwigner) ，以程式碼形式以類別的實例來表示 `JordanWignerEncoding` 。

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

模擬演算法取用的這種 Wigner 標記法格式 Q# 是使用者定義型別 `JordanWignerEncodingData` 。
在中 Q# ，此格式會傳遞至方便 `TrotterStepOracle` 的函式，此函式會使用 Trotter （Suzuki 整合器）傳回運算子將逼近時間演進，以及其執行所需的其他參數。

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

重要的是，這項實行會套用一些在 [模擬 Hamiltonian 使用量子電腦的電子結構](https://arxiv.org/abs/1001.3855) 時所討論的優化，並 [改善量子化學的量子演算法](https://arxiv.org/abs/1403.1539) ，以將所需的單一量子位輪替數目降至最低，並減少模擬錯誤。

## <a name="qubitization"></a>量子位化

量子位化是模擬的替代方法，會使用量子逐步解說中的想法來模擬量子 dynamics。
雖然量子位化需要比 Trotter 公式更多的量子位，但方法在演進時間和容錯能力上提供最佳調整。
基於這些原因，它已成為一般模擬 Hamiltonian dynamics 的最常用方法，也是解決電子結構問題的特殊方法。

概括而言，量子位化會透過下列步驟完成這項工作。
首先，讓 $H = \ sum_j h_j H_j $ 適用于單一和 Hermitian $H _j $ 和 $h _j \ge $0。
藉由執行一對反射，量子位化會實作用等於 $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1) }，$ $ （其中 $ | h | _1 = \ sum_j | h_j | $）的運算子。
下一步是要將逐步運算子的特徵值從 $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1) } $ 中轉換，其中 $E _k $ 是 $H $ 到 $e ^ {-iE_k t} $ 的特徵值。
您可以使用各種量子單數值轉換方法來達成此目的，包括 [量子信號處理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)。

或者，如果只需要靜態數量 (例如 Hamiltonian 的地面狀態能源) 則它會後綴將 [階段估計](xref:microsoft.quantum.libraries.characterization) 直接套用至 $W $，藉由採取結果的余弦值，從結果中估計地面狀態的能源。
這很重要，因為它可讓光譜轉換執行傳統方式，而不是使用量子單數值轉換方法。

在更詳細的層級上，量子位化的執行需要兩個可提供 Hamiltonian 介面的副程式。
與 Trotter （Suzuki）方法不同的是，這些副程式不是傳統的，且其執行必須使用 logarithmically 以上的量子位，而非以 Trotter 為基礎的模擬。

量子位化使用的第一個量子副程式稱為 $ \operatorname{Select} $，並承諾產生 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每個 $H _j $ 會假設為 Hermitian 和單一。
雖然這看起來可能會受到限制，但請記住，Pauli 運算子是 Hermitian 和單一的，因此量子化學模擬之類的應用程式自然會落在此架構中。
$ \Operatorname{Select} $ 作業（可能很令人驚訝）實際上是反映運算。
這可能是因為 $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $ 的事實，因為每個 $H _j $ 是單一和 Hermitian，因此具有特徵值 $ \pm $1。

第二個子程式稱為 $ \operatorname{Prepare} $。
雖然選取作業提供了時存取每個 Hamiltonian 詞彙的方法 $H _j $ 此準備副程式會提供方法來存取係數 $h _j $、\begin{equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}。
\end{equation} 然後，藉由使用已控制的階段閘道，我們會看到 $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{if} x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}。
$$

$ \Operatorname{Prepare} $ 作業不會直接在量子位化中使用，而是用來執行有關 $ \operatorname{Prepare} $ 建立 $ $ \begin{align} R &amp; = 1-2 \ 運算子名稱 {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} 之狀態的反映。
\end{align} $ $

您可以使用 $ \operatorname{Select} $ 和 $R $ 作業來表示「逐步運算子」（$W $），例如 $ $ W = \operatorname{Select} R、$ $，如此一來，就可以將相等的運算子 (最) 多等於 $e ^ {\pm i \cos ^ {-1} (H/| H | _1) } $。

在中，您可以輕鬆地設定這些副程式 Q# 。
例如，請考慮使用簡單的量子位橫向-Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。
在此情況下，會叫用 Q# 執行 $ \operatorname{Select} $ 作業的程式碼 <xref:Microsoft.Quantum.Canon.MultiplexOperations> ，而 $ \operatorname{Prepare} $ 作業則可以使用來執行 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> 。
您可以在[ Q# 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)中找到包含模擬 Hubbard 模型的範例。

針對任意化學問題手動指定這些步驟，需要投入大量的時間，這是使用化學程式庫避免的。
類似于上述的 Trotter-Suzuki 模擬演算法， `JordanWignerEncodingData` 會傳遞至方便的函式，以傳回 `QubitizationOracle` 逐步運算子，以及執行所需的其他參數。

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

重要的是，此執行 <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> 適用于指定為 Pauli 字串線性組合的任意 hamiltonian。
使用針對化學模擬優化的版本 <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> 。
此版本已經過優化，可將使用在 [量子線路中使用編碼電子 Spectra 的技巧，以線性 t 複雜度進行編碼](https://arxiv.org/abs/1805.03662)，以最小化 t 閘道的數目。
