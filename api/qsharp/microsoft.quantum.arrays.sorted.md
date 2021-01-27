---
uid: Microsoft.Quantum.Arrays.Sorted
title: 已排序函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845435"
---
# <a name="sorted-function"></a>已排序函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列時，會傳回該陣列的元素，並依指定的比較函式排序。

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="comparison--tt---bool"></a>比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比較兩個元素的函式，如果是，則會將其 `a` 視為小於或等於 `b` `comparison(a, b)` `true` 。


### <a name="array--t"></a>陣列： t []

要排序的陣列。



## <a name="output--t"></a>Output： t []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="example"></a>範例

下列程式碼片段會以遞增順序排序要進行的整數陣列：

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>備註

函式 `comparison` 假設為可轉移，因此，如果 `comparison(a, b)` 和 `comparison(b, c)` ，則 `comparison(a, c)` 會假設為。 如果這個屬性不存在，則此函式的輸出可能會不正確。

因為這是函式，所以即使兩個元素被視為相等，也會完全 determinstic 結果，也 `comparison` 就是當 `comparison(a, b)` 和 `comparison(b, a)` 都是時 `true` 。
尤其是，此函式所執行的排序保證是穩定的，因此，如果在 `a` `b` 和內的兩個專案都是以相同的順序出現在中，則也會在 `array` `comparison` `a` `b` 輸出中顯示。

例如：

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```