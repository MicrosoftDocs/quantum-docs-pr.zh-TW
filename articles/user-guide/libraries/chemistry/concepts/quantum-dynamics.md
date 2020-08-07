---
title: 量子 Dynamics
description: 瞭解配量 dynamics 和傳統 dynamics 之間的相似性和差異。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: e63ec497f2a7747e172d5fbdc249fe4064c482b6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869489"
---
# <a name="quantum-dynamics"></a>量子 Dynamics

量子機制主要是配量 dynamics 的研究，它會尋求瞭解初始量子狀態 $ \ket{\psi (0) } $ 如何隨著時間而改變 (請參閱量子運算上的[概念](xref:microsoft.quantum.concepts.dirac)檔，以取得 Dirac 標記法) 的詳細資訊。
具體而言，假設此初始條件為量子狀態、演進時間和量子 dynamical 系統的規格，則會搜尋量子狀態 $ \ket{\psi (t) } $。
在繼續說明「配量 dynamics」之前，請先回頭執行並思考一下「傳統 dynamics」，因為它可讓您深入瞭解量子機制與傳統 dynamics 的不同之處。

在傳統 dynamics 中，我們根據 $F (x，t) = ma = m\frac {\ dd ^ 2} {\dd t ^ 2} {x} (t) $，從牛頓的第二個法則中得知物件的位置，其中 $F (x，t) $ 是 force，而 $m $ 是加速。
然後，假設有一個初始位置 $x (0) $、演進時間 $t $，以及對物件採取動作的描述，我們就可以藉由解決 $x (t) $ 的牛頓方程式所指定的差異方程式，來尋找 $x ($) $。
以這種方式指定強制會有點棘手。
因此，我們通常會以系統的潛在能源來表示強制執行，這會提供 $-\ partial_x V (x，t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $。
因此，對於物件而言，系統的 dynamics 只會由可能的能源功能、物件品質和進化時間來指定。

較廣泛的語言通常是針對超過 $F = ma $ 的傳統 dynamics 而引進。
其中一個在量子機制中特別有用的公式是 Hamiltonian 的機制。
在 Hamiltonian 機制中，系統的總能源和 (一般化) 位置和 momenta 會提供描述任意傳統物件之動作所需的所有資訊。
具體而言，讓 $f (x，p，t) $ 是系統的通用位置 $x 的部分函式，並讓 $p $H x，p，t ($ 是 Hamiltonian 函數。
例如，如果我們採用 $f (x，p，t) = x (t) $ and $H (x，p，t) = p ^ 2 (t) /2m-V (x，t) $，則我們會復原上述有關 < 牛頓 dynamics 案例。
在一般性的情況下，我們會讓 \begin{align} \frac{d}{dt} f &= \ partial_t partial_x ( f + \ partial_p H \ partial_p f \\ \\ ，partial_x) \defeq \ & f + \\ {f，H \\ }。
\end{align} 這裡 $ \\ {f，H \\ } $ 稱為波和8，因為它在定義 dynamics 中扮演的中央角色[，所以](https://en.wikipedia.org/wiki/Poisson_bracket)會在傳統 dynamics 中出現 ubiquitously。

您可以使用完全相同的語言來描述量子 dynamics。
[Hamiltonian] 或 [總能源] 會完全指定任何已關閉之配量系統的動態。
不過，這兩個理論之間有一些顯著的差異。
在傳統的機制中 $x $ 和 $p $ 只是數位，而在量子機制中則不是。
事實上，他們甚至不會在 $xp \ne px $。

描述這些非通勤物件的正確數學概念是一個運算子，在這種情況下，$x $ 和 $p $ 只能接受一組離散的值，以符合矩陣的概念。
因此，為了簡單起見，我們會假設我們的量子系統是有限的，因此可以使用[向量和矩陣](xref:microsoft.quantum.concepts.vectors)加以描述。
我們會進一步要求將這些矩陣 Hermitian (表示矩陣的共軛轉置與原始矩陣) 相同。
這可保證矩陣的特徵值是實值;我們強制執行的條件，以確保當我們測量的數量類似位置時，我們不會取回虛數。

就像在配量機制中的位置和動力雷同必須由運算子取代，Hamiltonian 函式必須以運算子來取代。
例如，對於可用空間中的物件，我們 $H (x，p) = p ^ 2/2m $，而在配量機制中，Hamiltonian operator $ \hat{H} $ 是 $ \hat{H} = \hat{p} ^ 2/2m $，其中 $ \hat{p} $ 是動量運算子。
從這種觀點來看，從傳統到量子 dynamics 只需要以運算子取代一般 dynamics 中所使用的變數。
一旦我們藉由將一般傳統 Hamiltonian 轉換成配量語言來建立 Hamiltonian 運算子，我們就可以表達任意量子機械數量的動態 (例如，配量機械運算子) $ \hat{f} (t) $ via \begin{align} \frac{d}{dt} \hat{f} = \ partial_t \hat{f} + [\hat{f}，\hat{H}]，\end{align}，其中 $ [f，H] = fH-Hf $ 稱為 commutator。
這個運算式與上面所提供的傳統運算式完全相同，其差異在於會以 \\ \\ $f $ 和 $H $ 之間的 commutator 來取代波狀括弧 $ {f，H} $。
採用傳統 Hamiltonian 並使用它來尋找量子 Hamiltonian 的程式，在量子術語中稱為標準量化。

我們最感興趣的是哪些運算子 $f $？  其答案取決於我們要解決的問題。
可能要尋找的最實用數量是「量子狀態運算子」，如先前的概念檔中所討論的，可用來解壓縮我們想要瞭解 dynamics 的所有內容。
在執行這項作業之後 (並將結果簡化為其中一個具有純狀態) 的情況下，會找到量子狀態的 Schrödinger 方程式，\begin{align} i \ partial_t \ket{\psi (t) } = \hat{H} (t) \ket{\psi (t) }。
\end{align}

這個方程式雖然可能比上述的直覺比較簡單，但也可能是瞭解如何模擬量子或傳統電腦上的量子 dynamics 的最簡單運算式。
這是因為差異方程式的解決方案可以下列格式表示 (適用于 $t $) \begin{align} \ket{\psi (t) } = e ^ {-iHt} \ket{\psi (0) } 中的 Hamiltonian 是常數的情況。
\end{align} 這裡 $e ^ {-iHt} $ 是單一矩陣。
這表示有一個配量線路，可以設計來執行它，因為量子電腦可以緊密地逼近任何單一矩陣。
這種尋找配量線路以實作為時間演進運算子的動作 $e ^ {-iHt} $ 是通常稱為「量子模擬」，或特別是 dynamical 量子模擬。
