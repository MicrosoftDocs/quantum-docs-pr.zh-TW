---
uid: Microsoft.Quantum.Arrays.Filtered
title: 篩選函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221261"
---
# <a name="filtered-function"></a>篩選函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列和定義給陣列元素的述詞時，會傳回陣列，其中包含符合述詞的元素。

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="predicate--t---bool"></a>述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)

從 `'T` 到布林值的函式，用來篩選元素。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--t"></a>Output： t []

滿足述詞的 `'T[]` 元素陣列。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。

## <a name="remarks"></a>備註

函式是針對泛型型別定義的，也就是說，每當我們有陣列和述詞時，就 `'T[]` `'T -> Bool` 可以篩選元素。