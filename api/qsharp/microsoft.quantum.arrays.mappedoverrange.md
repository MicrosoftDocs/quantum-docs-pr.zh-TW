---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699450"
---
# <a name="mappedoverrange-function"></a>MappedOverRange 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


假設範圍和採用整數做為輸入的函式，則會傳回新的陣列，其中包含函式下範圍值的影像。

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>輸入

### <a name="mapper--int---t"></a>對應工具： [Int](xref:microsoft.quantum.lang-ref.int) -> t

中 `Int` `'T` 用來對應範圍值的函式。


### <a name="range--range"></a>範圍： [範圍](xref:microsoft.quantum.lang-ref.range)

整數的範圍。



## <a name="output--t"></a>Output： t []

由函式 `'T[]` 所對應的元素陣列 `mapper` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

函數的結果型別 `mapper` 。

## <a name="remarks"></a>備註

函數是針對泛型型別定義的，也就是說，每當我們有函式時， `mapper: Int -> 'T` 我們可以對應範圍的值，並產生型別的陣列 `'T[]` 。

## <a name="see-also"></a>另請參閱

- [。對應的](xref:Microsoft.Quantum.Arrays.Mapped)