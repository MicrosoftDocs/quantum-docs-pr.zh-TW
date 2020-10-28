---
title: 量子機器學習程式庫詞彙
description: 量子機器學習服務詞彙的詞彙
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 476e93e3737dee6ad8f3a97e8ffbcfb9b0012ee1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691522"
---
# <a name="quantum-machine-learning-glossary"></a>量子 Machine Learning 詞彙

以電路為中心的量子分類器定型是一種處理常式，其中包含許多需要相同 (或稍微放大) 數量的校正的程式，例如傳統分類器的定型。 我們在這裡定義了此訓練流程的主要概念和要素。

## <a name="trainingtesting-schedules"></a>定型/測試排程

在分類器定型的內容中， *排程* 會描述整體定型或測試集中的一部分資料樣本。 排程通常定義為範例索引的集合。

## <a name="parameterbias-scores"></a>參數/偏差分數

假設有一個候選參數向量和分類偏差，其 *驗證分數* 會相對於所選的驗證排程來測量，並以排程 s 中所有範例的情形計數來表示。

## <a name="hyperparameters"></a>超參數

模型定型程式是由稱為 *超參數* 的特定預先設定值所控制：

### <a name="learning-rate"></a>學習率

這是其中一個關鍵超參數。 它會定義目前的隨機漸層估計影響參數更新的程度。 參數更新差異的大小與學習速率成正比。 較小的學習率值會導致參數演進速度變慢，且聚合速度較慢，但過度大的 LR 值可能會中斷聚合，因為梯度下降永遠不會認可到特定的本機最小值。 雖然定型演算法會以自我調整方式將學習速率調整為某個程度，但為此選取良好的初始值是很重要的。 學習速率的一般預設初始值為0.1。 選取最佳的學習速率值是一種精細的 (請參閱，例如，Goodfellow 的第4.3 節。」、「深度學習」、MIT 按 2017) 。

### <a name="minibatch-size"></a>迷你批次大小

定義用於單一隨機漸層估計的資料樣本數。 迷你批次大小較大的值通常會導致更健全且更單純的聚合，但可能會減緩定型程式，因為任何一個漸層估計的成本與 minimatch 的大小成正比。 迷你批次大小的一般預設值為10。

### <a name="training-epochs-tolerance-gridlocks"></a>訓練 epoch、容錯、gridlocks

「Epoch」表示經過排程定型資料的一次完成。
每個定型執行緒的 epoch 數目上限 (請參閱下面) 應該有上限。 定型執行緒的定義是使用最佳的已知候選參數來終止 (，) 在 epoch 數目上限已執行時。 不過，當驗證排程的分類誤判率低於選擇的容錯時，這類訓練會稍早終止。 例如，假設分類誤判容錯為 0.01 (1% ) ;如果在2000範例的驗證集上，我們看到的情形少於20個，則表示已達到容錯層級。 如果候選模型的驗證分數尚未在 gridlock) 的數個連續 (epoch 中顯示任何改進，則定型執行緒也會提前終止。 Gridlock 終止的邏輯目前已硬式編碼。

### <a name="measurements-count"></a>度量計數

在量子裝置上估計定型/驗證分數和隨機漸層的元件，以預估需要適當可預見值的多個度量的量子狀態重迭。 度量的數目應調整為 $O (1/\ epsilon ^ 2) $，其中 $ \epsilon $ 是所需的估計錯誤。
根據經驗法則，初始測量計數可能大約 $ 1/\ .mbox {容錯} ^ 2 $ (查看上一個段落中的容錯定義) 。 如果漸層下降出現太不穩定，而且聚合太難達成，則必須將測量計數向上修改一次。

### <a name="training-threads"></a>定型執行緒

分類器定型公用程式的機率函數很少是凸出，這表示它在參數空間中通常會有許多本機 optima，可能會因為品質而大幅差異。 因為 SGD 程式只可融合到一個特定的最佳，所以請務必流覽多個起始參數向量。 機器學習中的常見作法是隨機初始化這類的起始向量。 Q#定型 API 接受這類起始向量的任意陣列，但基礎程式碼會依序探索它們。 在多核心電腦上，或事實上在任何平行運算架構上，建議您執行數個訓練 API 的呼叫，以 Q# 平行地在呼叫之間進行不同的參數初始化。

#### <a name="how-to-modify-the-hyperparameters"></a>如何修改超參數

在 QML 程式庫中，修改超參數的最佳方式是覆寫 UDT 的預設值 [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) 。 若要這樣做，我們會使用函式來呼叫它 [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) ，並套用運算子 `w/` 以覆寫預設值。 例如，若要使用100000測量和0.01 的學習率：

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
