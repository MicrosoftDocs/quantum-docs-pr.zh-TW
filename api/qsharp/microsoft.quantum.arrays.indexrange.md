---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845788"
---
# <a name="indexrange-function"></a>IndexRange 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>範例

下列 `for` 迴圈是相等的：

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```