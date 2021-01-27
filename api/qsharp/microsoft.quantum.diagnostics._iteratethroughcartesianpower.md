---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853572"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


透過笛卡兒乘積 [0，界限 [0]-1] × [0，界限 [1]-1] × [0，界限 [長度 (界限) -1]-1]，並針對笛卡兒乘積的每個元素呼叫 op (arr) 

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>輸入

### <a name="length--int"></a>長度： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

