---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220564"
---
# <a name="mostandtail-function"></a>MostAndTail 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列中除了一個和最後一個元素的元組。

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>輸入

### <a name="array--a"></a>陣列： ' A []

至少有一個元素的陣列。



## <a name="output--aa"></a>輸出： ( ' A []，' A) 

陣列中除了一個和最後一個元素的元組。

## <a name="type-parameters"></a>類型參數

### <a name="a"></a>' A

陣列元素的類型。