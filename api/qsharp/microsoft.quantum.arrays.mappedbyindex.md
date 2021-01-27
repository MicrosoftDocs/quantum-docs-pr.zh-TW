---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845657"
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

## <a name="example"></a>範例

下列兩行是相等的：

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

及

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>另請參閱

- [。對應的](xref:Microsoft.Quantum.Arrays.Mapped)