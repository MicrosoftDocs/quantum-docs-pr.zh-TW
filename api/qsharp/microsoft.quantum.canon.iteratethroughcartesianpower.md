---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206471"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在整數範圍的笛卡兒乘冪中，為每個索引套用一個運算。

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>描述

反復針對範圍的笛卡兒乘冪的每個元素，套用一項作業 `0..(bound - 1)` 。

## <a name="input"></a>輸入

### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

應產生範圍的笛卡兒乘冪 `0..(bound - 1)` 。


### <a name="bound--int"></a>系結： [Int](xref:microsoft.quantum.lang-ref.int)

要逐一查看的範圍規格，指定為範圍的長度。


### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

針對給定笛卡兒乘冪的每個元素呼叫的作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)