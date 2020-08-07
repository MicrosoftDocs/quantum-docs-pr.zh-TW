---
title: 量子機器學習程式庫
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 52c3f69fb99384270a27e57c4f32212d18bee1a4
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868894"
---
# <a name="quantum-machine-learning-glossary"></a>量子 Machine Learning 詞彙

以電路為中心的配量分類器的定型是一種程式，其中有許多移動元件需要相同的 (或稍微大一點的) 校正校準，而錯誤則是傳統分類器的定型。 我們將在此定義此訓練程式的主要概念和要素。

## <a name="trainingtesting-schedules"></a>訓練/測試排程

在分類器定型*排程*的內容中，會描述整體訓練或測試集中的資料樣本子集。 排程通常會定義為範例索引的集合。

## <a name="parameterbias-scores"></a>參數/偏差分數

假設有候選參數向量和分類偏差，其*驗證分數*會相對於所選的驗證排程來測量，並以排程中所有樣本上的數個 misclassifications 表示。

## <a name="hyperparameters"></a>超參數

模型定型程式是由稱為*超參數*的特定預先設定值所控制：

### <a name="learning-rate"></a>學習率

它是其中一個重要的超參數。 它會定義目前的隨機漸層估計會對參數更新造成多少影響。 參數更新差異的大小與學習速率成正比。 較小的學習速率值會導致較慢的參數進化和較慢的聚合，但過度大的 LR 值可能會中斷聚合，因為梯度下降永遠不會認可到特定的本機最小數目。 雖然學習速率是由定型演算法在某種程度上進行自我調整調整，但為其選取一個良好的初始值非常重要。 學習速率的一般預設初始值為0.1。 選取最佳的學習速率值是一個不錯的 (，例如，Goodfellow et al 的第4.3 節，「深度學習」，MIT 按下 2017) 。

### <a name="minibatch-size"></a>迷你批次大小

定義隨機漸層的單一估計使用多少資料樣本。 較大的迷你批次大小值通常會導致更強大且更單純的聚合，但可能會使定型程式變慢，因為任何一個漸層估計的成本會與 minimatch 大小成正比。 迷你批次大小的一般預設值是10。

### <a name="training-epochs-tolerance-gridlocks"></a>訓練 epoch、容錯、gridlocks

「Epoch」表示一次完成排程的定型資料。
每個定型執行緒的 epoch 數目上限 (見下面) 應為上限。 定型執行緒定義為在執行最大 epoch 數目時，終止具有最佳已知候選參數) 的 (。 不過，當驗證排程的分類誤判速率低於所選的容錯時，這類訓練會提早終止。 例如，假設分類誤判容錯為 0.01 (1% ) ;如果在2000樣本的驗證集上看到的 misclassifications 少於20個，則已達到容錯等級。 如果候選模型的驗證分數尚未顯示 (gridlock) 之數個連續 epoch 的任何改善，訓練執行緒也會提前終止。 Gridlock 終止的邏輯目前已硬式編碼。

### <a name="measurements-count"></a>測量計數

在配量裝置數量上預估訓練/驗證分數和隨機漸層的元件，以估計需要多次測量適當可預見值的量子狀態重迭。 量值的數目應該調整為 $O (1/\ epsilon ^ 2) $，其中 $ \epsilon $ 是所需的估計錯誤。
根據經驗法則，初始量測計可能大約是 $ 1/\ .mbox {容錯} ^ 2 $ (請參閱上一個段落) 中的容錯定義。 如果梯度下降變得太不穩定，而且收斂過於難以達成，則需要將測量計數向上修改。

### <a name="training-threads"></a>定型執行緒

這是分類器定型公用程式的機率函數非常少使用，這表示它在參數空間中通常會有許多本機 optima，品質可能會有顯著的差異。 由於 SGD 程式只能收斂到一個特定的最佳方式，因此請務必探索多個起始參數向量。 機器學習服務中的常見做法是隨機初始化這類啟動向量。 Q#定型 API 接受這類啟動向量的任意陣列，但基礎程式碼會依序進行探索。 在多核心電腦上，或實際上是在任何平行運算架構上，建議您 Q# 在呼叫之間，使用不同的參數初始化來平行執行數個訓練 API 的呼叫。

#### <a name="how-to-modify-the-hyperparameters"></a>如何修改超參數

在 QML 程式庫中，修改超參數的最佳方式是覆寫 UDT 的預設值 [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) 。 若要這樣做，我們會使用函式來呼叫它 [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) ，並套用運算子 `w/` 來覆寫預設值。 例如，若要使用100000測量和0.01 的學習率：
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
