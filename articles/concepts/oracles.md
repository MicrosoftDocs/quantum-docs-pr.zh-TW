---
title: 量子 Oracle
description: 瞭解如何使用並定義用來做為其他演算法輸入的「量子 oracles」、「黑色箱」作業。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904922"
---
# <a name="quantum-oracles"></a>量子 Oracles

Oracle $O $ 是「黑箱」作業，用來做為另一個演算法的輸入。
通常，這類作業會使用傳統函式來定義 $f： \\{0，1\\} ^ n \to \\{0，1\\} ^ m $，這會採用 $n $ 位二進位輸入，並產生 $m $ 位二進位輸出。
若要這麼做，請考慮特定的二進位輸入 $x = （x_{0}，x_{1}，\dots ..，x_ {n-1}） $。
我們可以將 qubit 狀態標示為 $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $。

我們可能會先嘗試定義 $O $，$O \ket{x} = \ket{f （x）} $，但這有幾個問題。
首先，$f $ 可能會有不同大小的輸入和輸出（$n \ne m $），因此套用 $O $ 會變更暫存器中的 qubits 數目。
第二，即使 $n = m $，函式也可能無法反轉：如果某些 $x \ne y $ 的 $f （x） = f （y） $，則 $O \ket{x} = O\ket {y} $，但 $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $。
這表示我們無法 $O ^ \dagger $ 中建立 adjoint 作業，而且 oracles 必須為其定義 adjoint。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>依其對計算基礎狀態的影響來定義 oracle
我們可以藉由引進第二個 $m $ qubits 的暫存器來處理這兩個問題，以保存我們的解答。
然後，我們將定義 oracle 在所有計算基礎狀態的效果：針對所有 $x \in \\{0，1\\} ^ n $ and $y \in \\{0，1\\} ^ m $，

$ $ \begin{align} O （\ket{x} \otimes \ket{y}） = \ket{x} \otimes \ket{y \oplus f （x）}。
\end{align} $ $

現在 $O = O ^ \dagger $ by 結構化，因此我們已解決這兩個先前的問題。

> [!TIP]
> 若要查看 $O = O ^ {\dagger} $，請注意 $O ^ 2 = \boldone $，因為 $a \oplus b \oplus b = a $ for all $a，b \in \{0，1\}$。
> 因此，$O \ket{x} \ket{y \oplus f （x）} = \ket{x} \ket{y \oplus f （x） \oplus f （x）} = \ket{x} \ket{y} $。

重要的是，以這種方式為每個計算基礎狀態 $ \ket{x}\ket{y} $ 定義 oracle，也會定義 $O $ 對任何其他狀態的作用。
這是從 $O $ （如所有配量作業）的事實開始，在其作用所在的狀態下是線性的。
請考慮 Hadamard 作業，例如，它是由 $H \ket{0} = \ket{+} $ 和 $H \ket{1} = \ket{-}$ 所定義。
如果我們想要知道 $ \ket{+} $ 的 $H $ 如何運作，我們可以使用 $H $ 是線性的。

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H （\ket{0} + \ket{1}） = \frac{1}{\sqrt{2}} （H\ket{0} + H\ket{1}） \\\\ & = \frac{1}{\sqrt{2}} （\ket{+} + \ket{-}） = \frac12 （\ket{0} + \ket{1} + \ket{0}-\ket{1}） = \ket{0}。
\end{align} $ $

在定義 oracle $O $ 的案例中，我們可以同樣地使用 $n + m $ qubits 上的任何 state $ \ket{\psi} $ 可以撰寫成

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \Alpha （x，y） \ket{x} \ket{y} \end{align} $ $

其中 $ \Alpha： \\{0，1\\} ^ n \times \\{0，1\\} ^ m \to \mathbb{C} $ 代表 state $ \ket{\psi} $ 的係數。 於是

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \Alpha （x，y） \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \Alpha （x，y） O \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \Alpha （x，y） \ket{x} \ket{y \oplus f （x）}。
\end{align} $ $

## <a name="phase-oracles"></a>階段 oracles
或者，我們可以根據 $O $ 的輸入套用_階段_，將 $f $ 編碼成 oracle $O $。
例如，我們可能會定義 $O $，例如 $ $ \begin{align} O \ket{x} = （-1） ^ {f （x）} \ket{x}。
\end{align} $ $ 如果某個階段在一開始就是以計算基礎狀態 $ \ket{x} $ 的方式運作，則此階段為全域階段，因此無法觀察。
但是，如果套用至重迭或做為受控制的作業，這類 oracle 可能是非常強大的資源。
例如，假設有一個階段 orcale $O _f $ 適用于單一 qubit 函數 $f $。
然後，$ $ \begin{align} O_f \ket{+} & = O_f （\ket{0} + \ket{1}）/\sqrt{2} \\\\ & = （（-1） ^ {f （0）} \ket{0} + （-1） ^ {f （1）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} （\ket{0} + （-1） ^ {f （1）-f （0）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} Z ^ {f （0）-f （1）} \ket{+}。
\end{align} $ $

更常見的情況是，可以放寬了 oracles 的兩個觀點來代表傳回實數的傳統函式，而不只是單一位。

選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用此 oracle。
例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依賴以第一種方式實作為的 oracle，而[Grover 的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依賴以第二種方式實施的 oracle。


如需更多詳細資訊，建議您在[Gilyén *et al*1711.00465](https://arxiv.org/abs/1711.00465)中進行討論。
