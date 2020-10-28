---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列舉函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699494"
---
# <a name="enumerated-function"></a>列舉函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


指定陣列時，會傳回新的陣列，其中包含原始陣列的元素以及每個專案的索引。

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>輸入

### <a name="array--telement"></a>陣列： ' TElement []

要列舉其元素的陣列。



## <a name="output--inttelement"></a>輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []

新的陣列，其中包含原始陣列的元素及其索引。

## <a name="type-parameters"></a>類型參數

### <a name="telement"></a>' TElement

陣列的元素類型。