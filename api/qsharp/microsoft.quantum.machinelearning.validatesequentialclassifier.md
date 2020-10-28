---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699684"
---
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier 操作

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


根據一組指定的預先標記範例，驗證指定的順序分類器。

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>輸入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要驗證的連續模型。


### <a name="samples--labeledsample"></a>範例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

用來驗證指定模型的範例。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

用來將每個範例編碼為連續分類器輸入的近似值誤差。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要用於分類每個樣本的度量數目。


### <a name="validationschedule--samplingschedule"></a>validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

從驗證集繪製樣本的排程。



## <a name="output--validationresults"></a>輸出： [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

給定驗證的結果。