---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699442"
---
# <a name="mostandtail-function"></a>MostAndTail 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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