---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699491"
---
# <a name="equala-function"></a>EqualA 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


如果有兩個相同類型的陣列和針對陣列的元素配對所定義的述詞，就會檢查陣列是否相等。

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>輸入

### <a name="equal--tt---bool"></a>等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

來自元組的函式， `('T, 'T)` `Bool` 用來檢查陣列的兩個元素是否相等。


### <a name="array1--t"></a>array1： t []

要比較的第一個陣列。


### <a name="array2--t"></a>array2： t []

要比較的第二個數組。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果和相等，則值為 `true` `array1` `array2` 。
也就是說，如果兩個數組都有相同的長度，而且所有元素都等於所定義的 `equal` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個陣列元素的類型。

## <a name="remarks"></a>備註

這個函式是針對泛型型別所定義;也就是說，只要有兩個數組和一個函式，此函式就 `'T[]` 會傳回 `equal: ('T, 'T) -> Bool` 一個 `Bool` 值，指出陣列是否相等。
針對兩個被視為相等的陣列，它們必須有相等的長度，而且陣列中相同位置的元素必須相等。