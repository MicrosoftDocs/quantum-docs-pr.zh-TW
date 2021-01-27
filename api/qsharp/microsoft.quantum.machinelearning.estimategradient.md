---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844389"
---
# <a name="estimategradient-operation"></a>EstimateGradient 操作

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


針對特定模型和指定編碼的輸入，預估順序分類器的定型漸層。

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>輸入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要估計其漸層的連續模型。


### <a name="encodedinput--stategenerator"></a>encodedInput： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

順序分類器的輸入，編碼為狀態準備作業。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

用來估計漸層的度量數目。



## <a name="output--double"></a>輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]

給定輸入和模型參數上定型漸層的估計值。

## <a name="remarks"></a>備註

這項作業會使用 Hadamard 測試和參數移位技術來預估漸層。