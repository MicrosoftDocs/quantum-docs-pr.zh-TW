---
uid: Microsoft.Quantum.Arrays.Excluding
title: 排除函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699489"
---
# <a name="excluding-function"></a>排除函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


傳回陣列，其中包含另一個陣列的元素，但不包括指定之索引清單中的元素。

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="remove--int"></a>remove： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列，表示應從輸出中排除的元素。


### <a name="array--t"></a>陣列： t []

輸出陣列中的值所採用的陣列。



## <a name="output--t"></a>Output： t []

陣列 `output` `output[0]` ，這是 `array` 其索引不會出現在中的第一個專案 `remove` ，例如 `output[1]` 第二個這類元素等等。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。