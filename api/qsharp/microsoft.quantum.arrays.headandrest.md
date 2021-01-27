---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848552"
---
# <a name="headandrest-function"></a>HeadAndRest 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列的第一個和所有其餘元素的元組。

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>輸入

### <a name="array--a"></a>陣列： ' A []

至少有一個元素的陣列。



## <a name="output--aa"></a>輸出： ( ' A，' A [] ) 

陣列的第一個和所有其餘元素的元組。

## <a name="type-parameters"></a>類型參數

### <a name="a"></a>' A

陣列元素的類型。