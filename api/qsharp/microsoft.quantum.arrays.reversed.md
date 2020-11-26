---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反轉函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220428"
---
# <a name="reversed-function"></a>反轉函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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