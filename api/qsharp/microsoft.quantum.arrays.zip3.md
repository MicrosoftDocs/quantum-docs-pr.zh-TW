---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219816"
---
# <a name="zip3-function"></a>Array.zip3 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Array.zip3 已被取代。 請改用 <xref:Microsoft.Quantum.Arrays.Zipped3>。

假設有三個數組，則會傳回3個元組的新陣列，讓每個3元組包含每個原始陣列的元素。

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>輸入

### <a name="first--t1"></a>first： t 1 []

陣列，其中包含每個元組的第一個元素值。


### <a name="second--t2"></a>第二： t 2 []

陣列，其中包含每個元組的第二個元素的值。


### <a name="third--t3"></a>第三： t 3 []

陣列，其中包含每個元組第三個元素的值。



## <a name="output--t1t2t3"></a>輸出： ( t 1，t 2，t 3) []

陣列，其中包含每個的表單3個元組 `(first[idx], second[idx], third[idx])` `idx` 。 如果三個數組的長度不相等，則輸出將會是輸入較短的時間長度。

## <a name="type-parameters"></a>類型參數

### <a name="t1"></a>T 1

第一個陣列元素的型別。
### <a name="t2"></a>T 2

第二個陣列元素的型別。
### <a name="t3"></a>T 3

第三個陣列元素的型別。

## <a name="see-also"></a>另請參閱

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)