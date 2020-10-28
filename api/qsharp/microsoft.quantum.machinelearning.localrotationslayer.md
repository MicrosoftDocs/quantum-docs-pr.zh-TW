---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700566"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


傳回未受控制的 (單一量子位) 旋轉的陣列，在指定的軸上，暫存器中的每個量子位都會有一次旋轉，並以相異模型參數參數化。

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

給定層處理的量子位數目。


### <a name="axis--pauli"></a>軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

給定圖層中每個旋轉的旋轉軸。



## <a name="output--controlledrotation"></a>輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

特定軸的受控制旋轉陣列，每個量子位都有一個 `nQubits` 。