---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211656"
---
# <a name="nqubitsrequired-function"></a>NQubitsRequired 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回套用指定順序分類器所需的量子位數目。

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a>輸入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可能套用順序分類器的暫存器大小下限。