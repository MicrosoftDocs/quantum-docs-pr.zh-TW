---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698199"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


透過笛卡兒乘積 [0，界限 [0]-1] × [0，界限 [1]-1] × [0，界限 [長度 (界限) -1]-1]，並針對笛卡兒乘積的每個元素呼叫 op (arr) 

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>輸入

### <a name="length--int"></a>長度： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

