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
ms.openlocfilehash: 65b0aa6a7f385765933d4d89ce34901f77cf76ec
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863092"
---
# <a name="introduction-to-quantum-machine-learning"></a>量子 Machine Learning 簡介

## <a name="framework-and-goals"></a>架構與目標

量子編碼和資訊處理是傳統機器學習量子分類器的強大替代方案。 尤其是，它可讓我們在量子暫存器中編碼相當於特徵數量的資料，並有系統地採用量子纏結做為運算資源，並採用類別推斷的量子測量。
以電路為中心的量子分類器是相當簡單的量子解決方案，結合了資料編碼與快速的 entangling/抽絲剝繭量子電路，接著測量以推斷資料範例的類別標籤。
其目標是要確保主體線路的傳統特性和儲存，以及線路參數的混合式量子/傳統訓練，即使是非常大的功能空間也是如此。

## <a name="classifier-architecture"></a>分類器架構

分類是受監督的機器學習工作，其目標是要推斷 \{ 特定資料範例的類別標籤 $ y_1、y_2、\ldots y_d \} $。 「訓練資料集」是範例 $ \mathcal{D} = \{ (x，y) } $ 的集合，其中包含已知預先指派的標籤。 此處 $x $ 是資料範例，$y $ 是其稱為「定型標籤」的已知標籤。
量子分類有點類似傳統的方法，包括三個步驟：
- 資料編碼
- 分類器狀態的準備工作
- 度量是因為測量的概率本質，這三個步驟必須重複多次。 分類器狀態的編碼和計算都是透過 *量子電路*來完成。 雖然編碼電路通常是資料驅動和無參數，但分類器電路包含一組足夠的 learnable 參數。 

在建議的解決方案中，分類器電路是由單一量子位的旋轉和雙量子位控制的旋轉所組成。 這裡的 learnable 參數是旋轉角度。 「旋轉」和「受控制的旋轉」閘道已知為量子計算的 *通用* ，這表示任何單一權數矩陣都可以分解成由這類閘道組成的夠長線路。

在建議的版本中，只支援一個電路，後面接著單一頻率的估計。
因此，解決方案是具有低度多項式核心的支援向量機器的量子類比。

![多層認知與以電路為中心的分類器](~/media/DLvsQCC.png)

簡單的量子分類器設計可以與傳統支援向量機器 (SVM) 解決方案。 在 SVM 的情況下，資料 $x 範例的推斷是使用最佳的核心表單 $ \sum \ Alpha_j k (x_j x) $，其中 $k $ 是特定的核心函式來完成。

相反地，量子分類器會使用預測 $p (y │ x、U ( \theta) # B3 = 〈 U ( \theta) x |M |U ( \theta) x 〉 $，這在精神中很類似，但技術上相當不同。 因此，使用簡單的調幅編碼時，$p (y │ x，U ( \theta) # B3 $ 是 amplitudes 中 $x $ 的二次形式，但此表單的係數不再獨立學習;它們會改為從電路的矩陣元素匯總 $U ( \theta) $，這通常會比向量 $x $ 的維度少很多的 learnable 參數 $ \theta $。 在原始功能中，$p (y │ x，U ( \theta) # B3 $ 的多項式程度可以增加至 $ 2 ^ l $，方法是在 $l $ 的 $x $ 複本上使用量子產品編碼。

我們的架構探討相當淺層的線路，因此必須 *快速 entangling* ，才能在所有範圍的資料功能之間抓取所有關聯性。 下圖顯示最有用的快速 entangling 電路元件的範例。 雖然具有此幾何的電路只包含 $3 n + 1 $ 閘道，但它所計算的單一權數矩陣可確保 $ 2 ^ n $ 功能之間有顯著的交叉交談。

![在5個量子位 (上快速 entangling 量子電路，) 有兩個迴圈層。](~/media/5-qubit-qccc.png)

上述範例中的線路包含6個單一量子位閘道 $ (G_1、\ldots、G_5;G_ {16}) $ 和 10 2-量子位閘道 $ (G_6，\ldots，G_ {15}) $。 假設每個閘道都定義了一個 learnable 參數，我們有16個 learnable 參數，而5量子位希伯特空間的維度是32。 當 $n $ 為奇數時，可輕鬆將這類線路幾何一般化至任何 $n $ 量子位暫存器，並為 $ 2 ^ n $ 維度功能空間產生具有 $3 n + 1 $ 參數的線路。

## <a name="classifier-training-as-a-supervised-learning-task"></a>分類定型作為受監督的學習工作

分類器模型的定型牽涉到尋找其作業參數的最佳值，使其能將正確定型標籤在定型範例中推斷的平均可能性最大化。
在這裡，我們只關心兩個層級的分類，亦即 $d = $2 的案例，以及只有兩個標籤 $y _1 y_2 $ 的類別。

> [!NOTE]
> 將我們的方法一般化至任意數目類別的謹守原則一切方法，就是將量子位取代為 qudits，也就是以 $d $ 基礎狀態的量子單位，以及使用 $d $-向測量的雙向度量。

### <a name="likelihood-as-the-training-goal"></a>作為定型目標的可能性

給定 learnable 量子線路 $U ( \theta) $，其中 $ \theta $ 是參數的向量，並以 $M $ 表示最後的測量值，正確標籤推斷的平均可能性為 $ $ \begin{align} \mathcal{L} ( \theta) = \frac {1} {| \mathcal{D} |} \left ( \ sum_ { (x，y_1) \In\mathcal{d}} P (M = y_1 |U ( \theta) x) + \ sum_ { (x，y_2) \in\mathcal{D}} P (M = y_2 |U ( \theta) x) \right) \end{align} $ $，其中 $P (M = y | z) $ 是測量 $y $ in 量子狀態 $z $ 的機率。
在這裡，它會後綴以瞭解可能性函式 $ \mathcal{L} ( \theta) $ 在 $ \theta $ 中是平滑的，且在任何 $ \ theta_j $ 中的衍生都可由基本上與用來計算可能性函式本身的相同量子通訊協定計算。 這可讓您將 $ \mathcal{L} ( \theta) $ 依梯度下降優化。

### <a name="classifier-bias-and-training-score"></a>分類偏差和定型分數

有了 $ \theta $ 中參數的某些中繼 (或最終) 值時，我們需要識別單一真正的值，$b $ 知道要進行推斷的 *分類偏差* 。 標籤推斷規則的運作方式如下： 
- 只有在 $P (M = y_2 時，才會將標籤 $y _2 $ 指派給範例 $x $U ( \theta) x) + b > $0.5 (RULE1)  (否則會指派標籤 $y _1 $) 

顯然 $b $ 必須在時間間隔 $ (-0.5、+ 0.5) $ 才有意義。

如果根據 RULE1 推斷 $x $ 的標籤與 $y $ 不同，則會將定型案例 $ (x，y) \in \mathcal{D} $ 視為 $b *分類誤判* 。 情形的整體數目是指定偏差 $b $ 的分類器 *定型分數* 。 *最佳*的分類偏差 $b $ 將定型分數降至最低。 由於預先電腦率估計 $ \{ P (M = y_2，因此很容易看出U ( \theta) x) | (x，* ) \in\mathcal{D} \} $，二進位搜尋可以在間隔 $ (-0.5，+ 0.5) $ 中找到最佳的分類偏差，最多可達 $ \ log_2 (| \mathcal{D} |) $ 步驟。

### <a name="reference"></a>參考

這種資訊應該足以開始使用程式碼。 但是，如果您想要深入瞭解此模型，請閱讀原始提案：「以 [*電路為中心的量子分類器」、Maria Schuld、Alex Bocharov、Krysta Svore 和 Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

除了您在後續步驟中會看到的程式碼範例，您也可以在[本教學](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/QuantumClassification)課程中開始探索量子分類 
