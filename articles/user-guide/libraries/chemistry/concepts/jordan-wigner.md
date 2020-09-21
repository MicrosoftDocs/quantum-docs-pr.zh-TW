---
title: 約旦-Wigner 標記法
description: 深入瞭解 Wigner 標記法，這會將 Hamiltonian 操作員對應到可在量子電腦上更容易執行的單一矩陣。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833851"
---
# <a name="jordan-wigner-representation"></a>約旦-Wigner 標記法

雖然第二個量化 Hamiltonian 是以 $a ^ \dagger $ (建立) 和 $a $ (annihilation) 方便表示，但這些作業不是量子電腦中的基本作業。
因此，如果我們希望它在量子電腦上執行，我們必須將操作員對應到可在量子電腦上執行的單一矩陣。
約旦– Wigner 標記法會提供一種地圖。
不過，其他的 Bravyi – Kitaev 標記法也存在，而且有其各自的優點和缺點。
Wigner 標記法的主要優點是它的簡化方式。

約旦 Wigner 標記法是要衍生的正向。
回想一下，state $ \ket {0} _j $ 表示微調 orbital $j $ 是空的，而 $ \ket {1} _j $ 表示它已被佔用。
這表示量子位可以自然地儲存特定微調 orbital 的職業。
然後，$a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ 和 $a ^ \ dagger_j \ket {1} _j = $0。
您可以輕鬆地確認 \begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} 、\nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} 、\end{align}，其中 $X _j $ 和 $Y _j $ 是以 Pauli $X $ 為目標的量子位 $Y $ 和-$j $ 運算子。

>[!NOTE]
> 在 Q# $ \ket {0} $ 狀態中，代表 $Z $ 運算子的 + 1 eigenstate。 在物理 $ \ket $ 的某些區域中， {0} 代表低能量地面狀態，因此是 $Z $ 運算子的-1 eigenstate。 因此，某些公式可能與熱門的文獻不同。

在化學程式庫中，我們使用 $ \ket {0} $ 表示空的旋轉 orbital。
這會顯示單一微調 orbital 很容易以量子電腦瞭解的單一矩陣來表示建立和 annihilation 運算子。
請注意，雖然 $X $ 和 $Y $ 是單一 $a ^ \dagger $，而 $a $ 則否。
稍後我們會看到這不會造成模擬的挑戰。

其中一個問題是，雖然上述結構適用于單一微調 orbital，但是具有兩個或多個微調 orbitals 的系統會失敗。
由於 Fermions 是 antisymmetic，我們知道 $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k 任何 dagger_j $ 和 $j $ 的 ^ \ $k $。
不過，$ $ \left ( \frac{X_j-iY_j} {2} \right) \left ( \frac{X_k-iY_k} {2} \right) = \left ( \frac{X_k-iY_k} {2} \right) \left ( \frac{X_j-iY_j} {2} \right) 。
$ $ 換言之，兩個建立運算子不會視需要進行反上運算。
您可以直接在種粗糙的方式中解決此情況。
修正程式是要注意的是，Pauli 運算子自然是反上的。
尤其是，$XZ =-ZX $ 和 $YZ =-ZY $。
因此，藉由將 $Z $ 運算子 interspersing 到運算子的結構中，我們可以模擬正確的反 commutation。
完整的結構如下所示： 

\begin{align} ^ \ dagger_1 &= \left ( \frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1、 \\ \\ ^ \ dagger_2 &= Z\otimes\left ( \frac{x-iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1、 \\ \\ ^ \ dagger_3 &= Z\otimes Z\otimes \left ( \frac{x-iy} {2} \right) \otimes 1 \otimes \cdots \otimes 1、 \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left ( \frac{x-iy} {2} \right) 。 \label{eq： JW} \end{align}

以 Pauli 運算子表達數位運算子（$n _j $）也很方便。
幸好，$Z $ 運算子的字串 (稱為約旦 Wigner 字串) 在進行這項替代之後取消。
在執行此 (並重新叫用 $X _jY_j = iZ_j $) 之後，我們已 \begin{equation} n_j = a ^ \ dagger_j a_j = \frac{ (1-Z_j) } {2} 。
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>以約旦 Wigner 標記法來建立 Hamiltonian

一旦叫用 Wigner 標記法，將 Hamiltonian 轉譯為 Pauli 運算子的總和是直接的。
其中一個只需要將 Fermionic Hamiltonian 中的每個 $a ^ \dagger $ 和 $a $ 運算子取代為上述 Pauli 運算子的字串。
當其中一個執行這項替換時，Hamiltonian 內只有五個詞彙類別。
這五個類別會對應到不同的方法，我們可以在 Hamiltonian 中挑選一個內文中的 $p、q $ 和 $p、q、r、s $，以及兩段內文。
這五個類別，在 $p>q>r>s $ 和實值 orbitals 的情況下，

\begin{align} h_ {pp} a_p ^ \dagger a_p &= \ sum_p \frac{h_ {pp}} {2} (1-Z_p) \\ \\ h_ {pq} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{h_ {pq}} {2} \left ( \ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left ( X_pX_q + Y_pY_q \right) \\ \\ h_ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{h_ {pqqr}} {2} \left ( \ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left ( X_pX_r + Y_pY_r \right) \left ( \frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{h_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

雖然以手動方式產生此類 Hamiltonian 只需要套用這些取代規則，但是針對大型分子（可以包含數百萬個 Hamiltonian 詞彙）並不可行。
或者，我們可以自動建立 `JordanWignerEncoding` 指定的 `FermionHamiltonian` Hamiltonian 標記法。

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

以這種形式建立 Hamiltonian 之後，我們就可以使用量子模擬演算法的主機，將由 $e ^ {-iHt} $ 產生的 dynamics，編譯成一系列的基本閘道， (在某些使用者可定義的誤差容錯) 內。
我們將在演算法檔中討論量子模擬、量子位化和 Trotter – Suzuki 公式的兩個最常用方法。 我們在 Hamiltonian 模擬程式庫中提供這兩種方法的執行方式。
