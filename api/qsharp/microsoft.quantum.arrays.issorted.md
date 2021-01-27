---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845727"
---
# <a name="issorted-function"></a>IsSorted 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列時，會傳回該陣列是否依照指定的比較函式的定義排序。

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>輸入

### <a name="comparison--tt---bool"></a>比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比較兩個元素的函式，如果是，則會將其 `a` 視為小於或等於 `b` `comparison(a, b)` `true` 。


### <a name="array--t"></a>陣列： t []

要檢查的陣列。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有在針對每對元素進行，以及 `a` `b` 該順序發生時，才 `array` `comparison(a, b)` 會是 `true` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="remarks"></a>備註

函式 `comparison` 假設為可轉移，因此，如果 `comparison(a, b)` 和 `comparison(b, c)` ，則 `comparison(a, c)` 會假設為。 如果這個屬性不存在，則此函式的輸出可能會不正確。