---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221108"
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