---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: b9e30e4e5bc23f56d9119083045967caff28f13a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699686"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel 操作

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


假設有連續分類器的結構，則會從特定模型開始訓練指定加上標籤之定型集的分類器。

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>輸入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要作為定型起點的連續模型。


### <a name="samples--labeledsample"></a>範例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

一組已加上標籤的定型資料，將用來執行定型。


### <a name="options--trainingoptions"></a>選項： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

定型時要使用的設定;如需詳細 @"microsoft.quantum.machinelearning.trainingoptions" 資訊，請參閱和 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 。


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

在定型步驟期間從定型資料選取樣本時要使用的取樣排程。


### <a name="validationschedule--samplingschedule"></a>validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

當您選取要產生最佳分類分數的起點時，從定型資料選取樣本時所要使用的取樣排程。



## <a name="output--sequentialmodelint"></a>Output： ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)，[Int](xref:microsoft.quantum.lang-ref.int)) 

- 指定分類器的參數化以及兩個類別之間的偏差，這兩者會對應到每個指定起點的最佳結果。
- 在最佳分類器模型中觀察到的遺漏數目。

## <a name="see-also"></a>另請參閱

- [MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)