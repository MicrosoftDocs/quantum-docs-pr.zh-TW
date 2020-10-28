---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699477"
---
# <a name="foreach-operation"></a>ForEach 操作

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


指定陣列和定義給陣列元素的作業時，會傳回新的陣列，其中包含作業下原始陣列的影像。

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>輸入

### <a name="action--t--u"></a>action： t => ' U 

從 `'T` 到的作業 `'U` 會套用至每個元素。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--u"></a>輸出： ' U []

作業所 `'U[]` 對應的元素陣列 `action` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。
### <a name="u"></a>' U

運算的結果類型 `action` 。

## <a name="remarks"></a>備註

作業是針對泛型型別定義的，也就是說，每當我們有陣列和作業時， `'T[]` `action : 'T -> 'U` 我們可以對應陣列的元素，並產生型別的新陣列 `'U[]` 。