---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: _RunSingleTrainingStep 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: c40bf6f1ceecef2cb196846b4f5a1c49023f1f74
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699714"
---
# <a name="_runsingletrainingstep-operation"></a>_RunSingleTrainingStep 操作

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


嘗試以迷你批次漸層的方向更新單一參數

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>輸入

### <a name="minibatch--labeledsamplestategenerator"></a>迷你批次： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []

迷你批次中已加上標籤之範例的容器


### <a name="options--trainingoptions"></a>選項： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)




### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--doublesequentialmodel"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) 

 (公用程式， (新的) 參數) 配對