---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699695"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


傳回沿著指定軸的單一控制旋轉陣列、在量子位的暫存器中排列迴圈，並以相異模型參數參數化。

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

給定層處理的量子位數目。


### <a name="axis--pauli"></a>軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

給定圖層中每個旋轉的旋轉軸。


### <a name="stride--int"></a>stride： [Int](xref:microsoft.quantum.lang-ref.int)

每個旋轉的目標和控制項索引之間的分隔。



## <a name="output--controlledrotation"></a>輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

兩個量子位控制的旋轉陣列，會在量子位的暫存器上配置迴圈 `nQubits` 。