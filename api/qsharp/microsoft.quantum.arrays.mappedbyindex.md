---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209922"
---
# <a name="mappedbyindex-function"></a>MappedByIndex 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果陣列和函式是針對陣列的索引元素所定義，則會傳回新的陣列，此陣列是由函式下原始陣列的影像所組成。

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>輸入

### <a name="mapper--intt---u"></a>對應工具： ([Int](xref:microsoft.quantum.lang-ref.int)，t) -> ' U

從到的函式， `(Int, 'T)` `'U` 用來對應元素及其索引。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--u"></a>輸出： ' U []

由函式 `'U[]` 所對應的元素陣列 `mapper` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。
### <a name="u"></a>' U

函數的結果型別 `mapper` 。

## <a name="see-also"></a>另請參閱

- [。對應的](xref:Microsoft.Quantum.Arrays.Mapped)