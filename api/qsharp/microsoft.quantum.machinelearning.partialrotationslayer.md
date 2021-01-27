---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852926"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回以相異模型參數參數化之指定軸的單一量子位旋轉陣列。

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>輸入

### <a name="idxsqubits--int"></a>idxsQubits： [Int](xref:microsoft.quantum.lang-ref.int)[]

要當做每個旋轉目標使用之量子位的索引。


### <a name="axis--pauli"></a>軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

給定圖層中每個旋轉的旋轉軸。



## <a name="output--controlledrotation"></a>輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

特定軸的受控制旋轉陣列，每個量子位都有一個 `nQubits` 。