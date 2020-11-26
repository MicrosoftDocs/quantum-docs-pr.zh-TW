---
uid: Microsoft.Quantum.Arrays.Mapped
title: 對應函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220734"
---
# <a name="mapped-function"></a>對應函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列和針對陣列元素定義的函式時，會傳回新的陣列，其中包含函式下原始陣列的影像。

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>輸入

### <a name="mapper--t---u"></a>對應工具： t-> ' U

從至的函式， `'T` `'U` 用來對應元素。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--u"></a>輸出： ' U []

由函式 `'U[]` 所對應的元素陣列 `mapper` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。
### <a name="u"></a>' U

函數的結果型別 `mapper` 。

## <a name="remarks"></a>備註

函式是針對泛型型別定義的，也就是說，每當我們有陣列和函式時， `'T[]` `mapper: 'T -> 'U` 我們可以對應陣列的元素，並產生型別的新陣列 `'U[]` 。