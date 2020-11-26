---
uid: Microsoft.Quantum.Arrays.Subarray
title: 子陣列函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220156"
---
# <a name="subarray-function"></a>子陣列函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


採用陣列和位置清單，並產生新的陣列，該陣列是從符合指定位置的原始陣列元素組成。

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="indices--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)[]

用來定義子陣列的整數清單。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--t"></a>Output： t []

專案的陣列 `out` ，其索引會對應至子陣列，因此為 `out[idx] == array[indices[idx]]` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。

## <a name="remarks"></a>備註

函數是針對泛型型別定義的，也就是，只要有陣列 `'T[]` 和定義子陣列的位置清單 `Int[]` 。
子陣列的結構是依據產生指定陣列的新深層複本，而不是維護參考。

如果 `Length(indices) < Length(array)` 為，則此函數會傳回的子集 `array` 。 另一方面，如果 `indices` 包含重複的元素，則 `array` 會同樣重複的對應元素。
如果 `indices` 和 `array` 的長度相同，此函數會提供的排列 `array` 。