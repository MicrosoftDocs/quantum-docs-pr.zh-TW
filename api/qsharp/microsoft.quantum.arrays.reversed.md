---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反轉函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699428"
---
# <a name="reversed-function"></a>反轉函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


建立陣列，其中包含與輸入陣列相同的元素，但以反向順序表示。

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t []

要以反轉順序複製其元素的陣列。



## <a name="output--t"></a>Output： t []

包含元素的陣列 `array[Length(array) - 1]` 。 `array[0]`.

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。