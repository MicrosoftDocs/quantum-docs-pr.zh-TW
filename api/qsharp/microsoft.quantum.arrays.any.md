---
uid: Microsoft.Quantum.Arrays.Any
title: 任何函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221652"
---
# <a name="any-function"></a>任何函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對陣列的元素定義陣列和述詞，會檢查陣列中至少有一個元素是否滿足述詞。

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>輸入

### <a name="predicate--t---bool"></a>述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)

中 `'T` `Bool` 用來檢查元素的函式。


### <a name="array--t"></a>陣列： t []

的元素陣列 `'T` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

套用至所有元素的述詞或函式的 `Bool` 值。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。

## <a name="remarks"></a>備註

函式是針對泛型型別定義的，也就是說，每當我們有陣列和函式時， `'T[]` `predicate: 'T -> Bool` 我們就可以產生一個 `Bool` 值，指出某個專案是否符合 `predicate` 。