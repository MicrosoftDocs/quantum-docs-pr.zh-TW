---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699472"
---
# <a name="indexof-function"></a>IndexOf 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


傳回陣列中第一個符合指定之述詞的第一個元素索引。 如果沒有這類元素，則傳回-1。

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>輸入

### <a name="predicate--t---bool"></a>述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)

在陣列元素上作用的述詞函式。


### <a name="arr--t"></a>arr： t []

要使用指定述詞搜尋的陣列。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

最小的索引 `idx` （例如 `predicate(arr[idx])` true），如果沒有這類元素，則為-1。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

