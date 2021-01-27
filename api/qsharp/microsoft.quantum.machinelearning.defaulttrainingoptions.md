---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855999"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回定型分類器的預設選項組。

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>輸出： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

定型分類器時，所使用的一組合理的預設定型選項。

## <a name="example"></a>範例

若要使用預設選項，但使用額外的度量，請使用 `w/` 運算子：

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```