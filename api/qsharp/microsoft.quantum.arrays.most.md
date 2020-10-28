---
uid: Microsoft.Quantum.Arrays.Most
title: 最多功能
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699443"
---
# <a name="most-function"></a>最多功能

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


建立等於輸入陣列的陣列，但最後一個陣列元素已卸載。

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t []

陣列，其優先于倒數第二個元素，以形成輸出陣列。



## <a name="output--t"></a>Output： t []

包含元素的陣列 `array[0..Length(array) - 2]` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。