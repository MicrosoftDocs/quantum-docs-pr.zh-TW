---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850915"
---
# <a name="unique-function"></a>Unique 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回不等於相鄰元素的新陣列。

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>描述

假設有一些元素陣列和函式測試是否相等，此函式會傳回新的陣列，其中會保留專案的相對順序，但是所有相等的相鄰元素都會篩選成隻有一個專案。

## <a name="input"></a>輸入

### <a name="equal--tt---bool"></a>等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比較兩個元素的函式， `a` 如果是，則視為等於 `b` `equal(a, b)` `true` 。


### <a name="array--t"></a>陣列： t []

要針對唯一元素篩選的陣列。



## <a name="output--t"></a>Output： t []

不等於相鄰元素的陣列。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="example"></a>範例

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>備註

如果有多個元素相等，但彼此不同，則輸出陣列中會出現多個專案。  使用此函式搭配 `Sorted` 來取得具有整體唯一元素的陣列。