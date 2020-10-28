---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699468"
---
# <a name="indexrange-function"></a>IndexRange 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


指定陣列時，會傳回該陣列的索引範圍，適用于 for 迴圈。

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>輸入

### <a name="array--telement"></a>陣列： ' TElement []

應傳回其索引範圍的陣列。



## <a name="output--range"></a>輸出： [範圍](xref:microsoft.quantum.lang-ref.range)

陣列所有索引的範圍。

## <a name="type-parameters"></a>類型參數

### <a name="telement"></a>' TElement

陣列的元素類型。