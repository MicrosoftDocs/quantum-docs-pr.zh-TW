---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699001"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


針對多個範圍的笛卡兒乘積中的每個索引套用作業。

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>描述

針對 `0..(bounds[0] - 1)` 、 `0..(bounds[1] - 1)` 、...、等笛卡兒乘積的每個元素反復套用作業 `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>輸入

### <a name="bounds--int"></a>界限： [Int](xref:microsoft.quantum.lang-ref.int)[]

陣列，指定要反復查看的範圍，並將每個範圍指定為整數長度。


### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

針對給定笛卡兒乘積的每個專案呼叫的作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)