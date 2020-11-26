---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220381"
---
# <a name="rest-function"></a>Rest 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


建立等於輸入陣列的陣列，但會卸載第一個陣列元素。

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t []

第二個元素到最後一個元素的陣列，其構成輸出陣列。



## <a name="output--t"></a>Output： t []

包含元素的陣列 `array[1..Length(array) - 1]` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。