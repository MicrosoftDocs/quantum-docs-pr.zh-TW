---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列舉函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848133"
---
# <a name="enumerated-function"></a>列舉函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>範例

下列 `for` 迴圈是相等的：

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```