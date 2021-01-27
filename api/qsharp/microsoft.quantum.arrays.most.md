---
uid: Microsoft.Quantum.Arrays.Most
title: 最多功能
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845573"
---
# <a name="most-function"></a>最多功能

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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