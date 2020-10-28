---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700595"
---
# <a name="nqubitsrequired-function"></a>NQubitsRequired 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


傳回套用指定順序分類器所需的量子位數目。

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a>輸入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可能套用順序分類器的暫存器大小下限。