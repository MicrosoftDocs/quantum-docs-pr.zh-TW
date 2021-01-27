---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848698"
---
# <a name="equala-function"></a>EqualA 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>範例

下列程式碼會檢查不同的陣列配對是否相等：

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>備註

這個函式是針對泛型型別所定義;也就是說，只要有兩個數組和一個函式，此函式就 `'T[]` 會傳回 `equal: ('T, 'T) -> Bool` 一個 `Bool` 值，指出陣列是否相等。
針對兩個被視為相等的陣列，它們必須有相等的長度，而且陣列中相同位置的元素必須相等。