---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700270"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


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