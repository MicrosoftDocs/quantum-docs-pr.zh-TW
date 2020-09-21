---
title: 量子 Dynamics
description: 瞭解量子 dynamics 與傳統 dynamics 之間的相似性和差異。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb54416ecdc38ea90999f33cb673c2c9e4c5f8d7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833868"
---
# <a name="quantum-dynamics"></a>量子 Dynamics

量子機制大多是量子 dynamics 的研究，旨在瞭解初始量子狀態 $ \ket{\psi (0) } $ 隨時間變化 (如需 Dirac 標記法) 的詳細資訊，請參閱量子運算上的 [概念](xref:microsoft.quantum.concepts.dirac) 檔。
具體來說，假設此初始狀況為量子狀態、量子 dynamical 系統的演進時間和規格，則會尋找量子狀態 $ \ket{\psi (t) } $。
在繼續說明量子 dynamics 之前，最好先回頭考慮傳統 dynamics，因為它可讓您深入瞭解量子機制與傳統 dynamics 有何不同。

在傳統 dynamics 中，我們知道，物件的位置會根據 $F 的 (x、t) = ma = m\frac {\ dd ^ 2} {\dd t ^ 2} {x} (t) $，其中 $F (x，t) $ 是強制，$m $ 是最大的 $a $ 是加速。
然後，假設有一個初始位置 $x (0) $、演進時間 $t $ 和對物件採取動作的說明，我們可以藉由解決 $x () $ 的牛頓方程式所指定的差異方程式，找出 $x (t) $。
以這種方式指定強制會有點棘手。
因此，我們通常會根據系統的潛在能源來表達力，這會提供我們 $-\ partial_x V (x，t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $。
因此，對於物件而言，系統的 dynamics 只會由可能的能源功能、粒子品質和演進時間來指定。

通常會針對超越 $F = ma $ 的傳統 dynamics 引進更廣泛的語言。
其中一種形式特別適用于量子機制，它是 Hamiltonian 的機制。
在 Hamiltonian 機制中，系統的總能源和 (一般化) 位置和 momenta 會提供描述任意傳統物件之動作所需的所有資訊。
具體來說，讓 $f (x、p、t) $ 是通用位置的部分函式，$x $ 和 momenta $p $ 系統，並讓 $H (x、p、t) $ 成為 Hamiltonian 函數。
例如，如果我們採用 $f (x、p、t) = x (t) $ 和 $H (x、p、t) = p ^ 2 (t) /2m-V (x，t) $，則我們會復原上述有關 < 牛頓 dynamics 案例。
在通用性中，我們接著將 \begin{align} \frac{d}{dt} f &= \ partial_t f ( \ partial_x H \ partial_p f + \ partial_p H \ partial_x f) \\ \\ & \defeq \ partial_t f + \\ {f，H \\ }。
\end{align} 這裡的 $ \\ {f，H \\ } $ 稱為波氏 [括弧](https://en.wikipedia.org/wiki/Poisson_bracket) ，而且因為它在定義 dynamics 時所扮演的中央角色，所以會以傳統 dynamics 顯示 ubiquitously。

您可以使用完全相同的語言來描述量子 dynamics。
Hamiltonian 或總能源會完全指定任何已關閉之量子系統的 dynamics。
不過，這兩個理論之間有一些重大的差異。
在傳統的機制中 $x $ 和 $p $ 僅是數位，而在量子機制中則不是。
其實，它們甚至不會像是 $xp \ne px $。

描述這些非通勤物件的正確數學概念是一個運算子，在這種情況下，$x $ 和 $p $ 只能採用一組離散的值，與矩陣的概念相符。
因此為了簡單起見，我們假設我們的量子系統是有限的，因此可使用 [向量和矩陣](xref:microsoft.quantum.concepts.vectors)加以描述。
此外，我們還需要將這些矩陣 Hermitian (表示矩陣的共軛變換與原始矩陣) 相同。
這可確保矩陣的特徵值是實值;我們強加的條件，可確保當我們測量數量（例如位置）時，我們不會取回虛數。

就像量子機制中的位置和動量的雷同必須由運算子取代，Hamiltonian 函式必須以同樣的方式取代。
例如，針對可用空間中的物件，我們 $H (x、p) = p ^ 2/2m $，而在量子機制中，Hamiltonian operator $ \hat{H} $ 是 $ \hat{H} = \hat{p} ^ 2/2m $，其中 $ \hat{p} $ 是動量運算子。
從這個觀點來看，從傳統到量子 dynamics 都只需要以運算子取代一般 dynamics 中所使用的變數。
藉由將一般的傳統 Hamiltonian 轉譯為量子語言來建立 Hamiltonian 運算子之後，我們就可以表達任意量子機械數量的動態 (例如量子機械運算子) $ \hat{f} (t) $ via \begin{align} \frac{d}{dt} \hat{f} = \ partial_t \hat{f} + [\hat{f}，\hat{H}]、\end{align}，其中 $ [f，H] = fH-Hf $ 稱為 commutator。
此運算式與上面所提供的傳統運算式完全相同，但會將波狀括弧 $ \\ {f，H \\ } $ 取代為 $f $ 和 $H $ 之間的 commutator。
採用傳統 Hamiltonian 並使用它來尋找量子 Hamiltonian 的程式，在量子術語中稱為標準量化。

我們最感興趣的操作員 $f $？  這個問題的答案取決於我們要解決的問題。
可能要尋找的最實用數量是量子狀態運算子，如先前的概念檔中所討論，可以用來解壓縮我們想要瞭解 dynamics 的所有專案。
在執行此 (，並將結果簡化為一個具有純狀態) 的情況下，會找到量子狀態的薛丁格方程式 \begin{align} i \ partial_t \ket{\psi (t) } = \hat{H} (t) \ket{\psi (t) }。
\end{align}

雖然這個方程式可能比較不直覺，但可能會產生最簡單的運算式，以瞭解如何在量子或傳統電腦上模擬量子 dynamics。
這是因為差異方程式的解決方案可以用下列形式表示 (適用于 $t $) \begin{align} \ket{\psi (t) } = e ^ {-iHt} \ket{\psi (0) } 中的 Hamiltonian 是常數的情況。
\end{align} 這裡 $e ^ {-iHt} $ 是單一矩陣。
這表示有一個量子電路可以設計來執行，因為量子電腦可以大致接近任何單一矩陣。
這種尋找量子線路以實行量子時間演進運算子的動作 $e ^ {-iHt} $ 通常稱為量子模擬，或特別 dynamical 量子模擬。
