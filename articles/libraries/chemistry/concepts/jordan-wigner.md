---
title: 約旦-Wigner 標記法
description: 瞭解 Wigner 標記法，這會將 Hamiltonian 操作員對應到可更輕鬆地在量子電腦上執行的單一矩陣。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 17cb473c6d33e3356d5da886f47985c3828d4d1f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904514"
---
# <a name="jordan-wigner-representation"></a>約旦-Wigner 標記法

雖然第二個量化 Hamiltonians 在 $a ^ \dagger $ （建立）和 $a $ （annihilation）方面方便呈現，但這些作業不是量子電腦中的基本作業。
因此，如果我們想要在量子電腦上執行它們，我們需要將操作員對應到可在量子電腦上執行的單一矩陣。
約旦– Wigner 標記法會提供這種對應。
不過，其他人（例如 Bravyi – Kitaev 標記法）也存在，而且有自己的相對優點和缺點。
Wigner 標記法的主要優點是它的簡單性。

Wigner 標記法是直接衍生的。
回想一下，state $ \ket{0}_j $ 表示微調 orbital $j $ 是空的，而 $ \ket{1}_j $ 表示它已被佔用。
這表示 qubits 可以自然地儲存指定微調 orbital 的職業。
接著，$a ^ \ dagger_j \ket{0}_j = \ket{1}_j $ and $a ^ \ dagger_j \ket{1}_j = $0。
您可以輕鬆地驗證 \begin{align} ^ \ dagger_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j-iY_j}{2}，\nonumber\\\\ a_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}，\end{align}，其中 $X _j $ 和 $Y _j $ 是以 Pauli $X $ 為目標的 Qubit $Y $ 和-$j $ 運算子。

>[!NOTE]
> 在 Q # 中，$ \ket{0}$ state 代表 $Z $ 運算子的 + 1 eigenstate。 在物理 $ \ket{0}$ 的某些區域中，代表低能量地面狀態，因此是 $Z $ 運算子的-1 eigenstate。 因此，某些公式可能會與熱門的文獻不同。

在化學程式庫中，我們使用 $ \ket{0}$ 來代表未佔用的微調 orbital。
這表示針對單一微調 orbital，很容易就能根據量子電腦瞭解的單一矩陣來呈現建立和 annihilation 運算子。
請注意，雖然 $X $ 和 $Y $ 是單一 $a ^ \dagger $，而 $a $ 則不是。
我們稍後會看到這不會造成模擬的挑戰。

其中一個問題是，雖然上述的結構適用于單一微調 orbital，但有兩個或更多微調 orbitals 的系統會失敗。
由於 Fermions 是 antisymmetic，因此我們知道 $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k 任何 dagger_j $ 和 $j $ 的 ^ \ $k $。
不過，$ $ \left （\frac{X_j-iY_j}{2}\right） \left （\frac{X_k-iY_k}{2}\right） = \left （\frac{X_k-iY_k}{2}\right） \left （\frac{X_j-iY_j}{2}\right）。
$ $ 換句話說，這兩個建立運算子不會視需要進行反上運算。
這可以在種粗糙的情況下，以簡單明瞭的方式來補救。
修正程式是要注意，Pauli 運算子自然地會進行反上運算。
特別是，$XZ =-ZX $ 和 $YZ =-ZY $。
因此，藉由將 $Z $ 運算子 interspersing 到運算子的結構中，我們可以模擬正確的反 commutation。
完整的結構如下所示： 

\begin{align} a ^ \ dagger_1 & = \left （\frac{X-iY}{2}\right） \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \ dagger_2 & = Z\otimes\left （\frac{X-iY}{2}\right） \otimes 1 \ otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \ dagger_3 & = Z\otimes Z\otimes \left （\frac{X-iY}{2}\right） \otimes 1 \otimes \cdots \otimes 1，\\\\ & \vdots\\\\ ^ \ dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z \otimes \left （\frac{X-iY}{2}\right）。 \label{eq： JW} \end{align}

在 Pauli 運算子方面，表達數位運算子（$n _j $）也很方便。
幸好，$Z $ operators （稱為 Wigner 字串）的字串會在進行這項替代之後取消。
在執行此程式（並重新叫用 $X _jY_j = iZ_j $）之後，我們 \begin{equation} n_j = a ^ \ dagger_j a_j = \frac{（1-Z_j）}{2}。
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>在約旦中建立 Hamiltonians-Wigner 標記法

一旦叫用 Wigner 標記法，將 Hamiltonian 轉換為 Pauli 運算子的總和，就會直接向前邁進。
其中一種方式就是將 Fermionic Hamiltonian 中的每個 $a ^ \dagger $ 和 $a $ 運算子取代為上述 Pauli 運算子的字串。
當其中一個執行此替代時，Hamiltonian 中只有五個詞彙類別。
這五個類別會對應到不同的方法，我們可以在 Hamiltonian 的單一主體和兩個內文詞彙中挑選 $p、q $ 和 $p、q、r、s $。
這五個類別，在 $p > q > r > s $ 和實值 orbitals 的情況下，

\begin{align} h_ {pp} a_p ^ \dagger a_p & = \ sum_p \frac{h_ {pp}}{2}（1-Z_p）\\\\ h_ {pq} （a_p ^ \dagger a_q + a ^ \ dagger_q a_p） & = \frac{h_ {pq}}{2}\left （\ prod_ {j = q + 1} ^ {p-1} Z_j \right） \left （X_pX_q + Y_pY_q \right）\\\\ h_ {pqqp} n_p n_q & = \frac{h_ {pqqp}}{4}\left （1-Z_p-Z_q + Z_pZ_q \right）\\\\ H_ {pqqr}} & \frac{（\ h_ {j =r + 1} ^ {p-1} Z_j \right） \left （X_pX_r + Y_pY_r \right） \left （\frac{1-Z_q}{2}\right）\\\\ H_ {pqrs} & = \frac{h_ {pqrs}}{8}\ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big （XXXX-XXYY + XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big） \end{align}{2}

雖然只是以手動方式產生這類 Hamiltonians 需要套用這些取代規則，但在大型分子驅使分子中可能會包含數百萬 Hamiltonian 詞彙，這是不可行的。
或者，我們可以根據 Hamiltonian 的 `FermionHamiltonian` 標記法，自動建立 `JordanWignerEncoding`。

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

在此表單中建立 Hamiltonians 之後，我們可以使用一系列的量子模擬演算法，將 $e ^ {-iHt} $ 所產生的 dynamics 編譯成一系列的基本閘道（在某些使用者可定義的容錯範圍內）。
我們會在演算法檔中討論量子模擬、qubitization 和 Trotter – Plat'home co. 公式的兩個最常用方法。 我們會在 Hamiltonian 模擬程式庫中提供這兩種方法的執行。
