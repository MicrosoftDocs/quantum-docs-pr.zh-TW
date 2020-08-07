---
title: 量子機器學習程式庫
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9a24d0b4145d0db2fd8c4e16be807165fff5fb32
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868911"
---
# <a name="introduction-to-quantum-machine-learning"></a>量子 Machine Learning 簡介

## <a name="framework-and-goals"></a>架構與目標

資訊的配量編碼和處理是傳統機器學習服務配量分類器的強大替代方式，特別是在配量暫存器中編碼相對於功能數目簡明的資料，並有系統地將量子會任何牽連當做計算資源，並採用類別推斷的量子測量。
以線路為中心的配量分類器是一個相當簡單的量子解決方案，它結合了資料編碼與快速的 entangling/抽絲剝繭配量電路，再加上測量來推斷資料範例的類別標籤。
其目標是要確保主旨線路的傳統特性和儲存體，以及即使是非常大的功能空間，也可以混合使用線路參數的混合式量子/傳統訓練。

## <a name="classifier-architecture"></a>分類器架構

分類是受監督的機器學習工作，其目標是要推斷類別標籤 $ \{ y_1、y_2、\ldots y_d \} $ 的特定資料範例。 「訓練資料集」是範例 $ \mathcal{D} = \{ (x，y) } $ 的集合，其中包含已知的預先指派標籤。 這裡 $x $ 是資料樣本，$y $ 是其已知的標籤，稱為「定型標籤」。
與傳統方法有點相似，配量分類包含三個步驟：
- 資料編碼
- 分類器狀態的準備工作
- 因測量的概率性質而產生的測量，這三個步驟必須重複多次。 量測可能會視為相當於非線性啟用的量子。
分類器狀態的編碼和計算都是透過配量*線路*來完成。 雖然編碼線路通常是資料驅動和無參數，但分類器電路包含一組足夠的 learnable 參數。 

在提議的解決方案中，分類器電路是由單一 qubit 旋轉和兩個 qubit 控制的旋轉所組成。 這裡的 learnable 參數是旋轉角度。 「旋轉」和「受控制」旋轉閘道已知為*通用*來進行量子計算，這表示任何單一權數矩陣都可以分解成夠長的線路，其中包含這類閘道。

![多層認知與以電路為中心的分類器](~/media/DLvsQCC.png)

我們可以將此模型與多層認知比較，以進一步瞭解基本結構。 在認知中，預測項 $p (y | x，\theta) $ 是由權數 $ \theta $ 的集合所參數化，用以判斷連接非線性啟動函數 (神經) 的線性函式。 這些參數可以定型以建立模型。 在輸出層，我們可以使用非線性啟動函式（例如 softmax）來取得屬於類別的範例機率。 在以線路為中心的分類器中，預測是由單一 qubit 的旋轉角度和模型電路的雙 qubit 控制旋轉所參數化。 以類似的方式，這些參數可透過混合式配量/傳統版本的漸層下降演算法來定型。 若要計算輸出，而不使用非線性啟動函式，會在受控制的旋轉之後，透過讀取特定 qubit 的重複測量來取得類別的機率。 為了在量子狀態中編碼傳統資料，我們使用可控制的編碼電路來準備狀態。

我們的架構探討相當淺層的線路，因此必須*快速 entangling* ，才能在所有範圍的資料功能之間捕捉所有關聯性。 下圖顯示最實用的快速 entangling 電路元件範例。 雖然具有此幾何的電路只包含 $3 n + 1 $ 閘道，但它所計算的單一權數矩陣可確保 $ 2 ^ n $ 功能之間有顯著的交叉交談。

![在具有兩個迴圈層) 的5個 qubits (上快速 entangling 配量線路。](~/media/5-qubit-qccc.png)

上述範例中的線路包含6個單一 qubit 閘道 $ (G_1、\ldots、G_5;G_ {16}) $ 和 10 2-qubits 閘道 $ (G_6、\ldots、G_ {15}) $。 假設每個閘道都是以一個 learnable 參數定義的，我們有16個 learnable 參數，而 5 qubit 希伯特空間的維度是32。 當 $n $ 是奇數時，這類電路幾何可以輕鬆一般化到任何 $n $ qubit 暫存器，產生 $3 n + 1 $ 參數的線路，適用于 $ 2 ^ n $ 維度的功能空間。

## <a name="classifier-training-as-a-supervised-learning-task"></a>分類定型做為監督式學習工作

分類器模型的定型包括尋找其作業參數的最佳值，使其最大化在定型範例中推斷正確定型標籤的平均可能性。
在這裡，我們只關心兩個層級分類，也就是 $d = $2，而只有兩個標籤 $y _1，y_2 $ 的類別。

> [!NOTE]
> 將我們的方法一般化為任意數目類別的原則方法，就是將 qubits 取代為 qudits （也就是具有 $d $ 基礎狀態的配量單位），以及使用 $d $ 向測量的雙向測量。

### <a name="likelihood-as-the-training-goal"></a>定型目標的可能性

假設 learnable 配量線路 $U ( \theta) $，其中 $ \theta $ 是參數的向量，並以 $M $ 來表示最後的測量，正確標籤推斷的平均可能性為 $ $ \begin{align} \mathcal{L} ( \theta) = \frac {1} {| \mathcal{D} |} \left ( \ sum_ { (x，y_1) \In\mathcal{d}} P (M = y_1 |U ( \theta) x) + \ sum_ { (x，y_2) \in\mathcal{D}} P (M = y_2 |U ( \theta) x) \right) \end{align} $ $，其中 $P (M = y | z) $ 是測量量子狀態 $y $ 中 $z $ 的機率。
在這裡，它尾碼瞭解 $ \theta $) $ \mathcal{L} ( \theta 的機率很平滑，而且在任何 $ \ theta_j $ 中的衍生都可以由基本上與用於電腦率函數本身相同的量子通訊協定計算。 這可讓您優化 $ \mathcal{L} ( \theta) $ by 梯度下降。

### <a name="classifier-bias-and-training-score"></a>分類偏差和定型分數

在 $ \theta $ 中，有一些參數的中繼 (或最後) 值，我們需要識別單一實值 $b $ 知道做為*分類偏差*，以進行推斷。 標籤推斷規則的運作方式如下： 
- 只有在 $P (M = y_2 時，才會將 $x $ 的範例指派 $y _2 $U ( \theta) x) + b > $0.5 (RULE1)  (否則會指派標籤 $y _1 $) 

顯然 $b $ 必須在間隔 $ (-0.5，+ 0.5) $ 才有意義。

如果在每個 RULE1 中針對 $x $ 所推斷的標籤實際上與 $y $ 不同，則定型案例 $ (x，y) \in \mathcal{D} $ 會視為 $b*分類誤判*。 Misclassifications 的整體數目是指定偏差 $b $ 的分類器*定型分數*。 *最佳*的分類偏差 $b $ 可將定型分數降至最低。 只要預先電腦率估計 $ \{ P (M = y_2，就很容易看出U ( \theta) x) | (x，* ) \in\mathcal{D} \} $，二進位搜尋可在間隔 $ (-0.5、+ 0.5) $ 中找到最多 $ \ log_2 (| \mathcal{D} |) $ 步驟，以達到最佳的分類偏差。

### <a name="reference"></a>參考

這種資訊應該足以開始使用程式碼。 不過，如果您想要深入瞭解此模型，請閱讀原始提案： ' 以[*線路為中心的量子分類器 '，Maria Schuld，Alex Bocharov，Krysta Svore 和 Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
