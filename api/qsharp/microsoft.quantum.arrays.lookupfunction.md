---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220768"
---
# <a name="lookupfunction-function"></a>LookupFunction 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列時，會傳回傳回該陣列元素的函式。

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t []

要表示為查閱函數的陣列。



## <a name="output--int---t"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int) -> t

`f`這樣的函式 `f(idx) == f[idx]` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的型別，以 lookup 函數表示。

## <a name="remarks"></a>備註

此函式主要適用于與以函式 `Int -> 'T` 作為其引數的函式和作業交互操作。 這種情況很常見，例如，在產生器表示程式庫中，函式是用來避免需要在記憶體中記錄整個陣列。