---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842772"
---
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


要用於定型量子分類器的選項組合。

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>命名專案

### <a name="learningrate--double"></a>LearningRate： [Double](xref:microsoft.quantum.lang-ref.double)

在定型步驟期間更新模型參數時，應重新調整漸層的學習速率。
### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

以量子狀態準備範例時所要使用的近似值容錯。
### <a name="minibatchsize--int"></a>MinibatchSize： [Int](xref:microsoft.quantum.lang-ref.int)

要在每個定型迷你批次中使用的樣本數目。
### <a name="nmeasurements--int"></a>NMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

測量每個分類結果以預估分類機率的次數。
### <a name="maxepochs--int"></a>MaxEpochs： [Int](xref:microsoft.quantum.lang-ref.int)

要為每個模型定型的 epoch 數目上限。
### <a name="maxstalls--int"></a>MaxStalls： [Int](xref:microsoft.quantum.lang-ref.int)

在失敗之前，允許訓練 epoch 停止 (大約零梯度) 的最大次數。
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor： [Double](xref:microsoft.quantum.lang-ref.double)

重試更新之前，要調整停止的模型的數量。
### <a name="scoringperiod--int"></a>ScoringPeriod： [Int](xref:microsoft.quantum.lang-ref.int)

計分點之間要執行的漸層步驟數目。
為了達到最佳精確度，請設定為1。
### <a name="verbosemessage--string---unit"></a>VerboseMessage： [字串](xref:microsoft.quantum.lang-ref.string) -> [單位](xref:microsoft.quantum.lang-ref.unit)

可以用來提供詳細資訊意見反應的函數。

## <a name="remarks"></a>備註

此 UDT 不應該直接建立，而是藉由呼叫 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 然後使用 `w/` 運算子來覆寫不同的預設值來指定。

例如，若要使用100000度量和最多8個定型 epoch：

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>參考資料

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)