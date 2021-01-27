---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847401"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述以其目標和控制索引、旋轉軸和索引至模型參數向量的控制旋轉。

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>命名專案

### <a name="targetindex--int"></a>TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)

此受控制旋轉之目標量子位的索引。
### <a name="controlindices--int"></a>ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]

這項旋轉的控制項量子位索引陣列。
### <a name="axis--pauli"></a>軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

此旋轉的軸。
### <a name="parameterindex--int"></a>ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)

模型參數向量的索引，描述這個旋轉的角度。

## <a name="example"></a>範例

以下代表在暫存器中第一個量子位的 $X $ 軸的旋轉、第二個量子位所控制的，以及連續模型中第四個參數所指定的角度：

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>備註

您可以設定 `ControlIndices` 為空的索引陣列來表示無法控制的旋轉 `new Int[0]` 。