---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848564"
---
# <a name="head-function"></a>Head 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列的第一個元素。

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>輸入

### <a name="array--a"></a>陣列： ' A []

取得第一個元素的陣列。 陣列的長度至少必須為1。



## <a name="output--a"></a>輸出： ' A

陣列的第一個元素。

## <a name="type-parameters"></a>類型參數

### <a name="a"></a>' A

陣列元素的類型。