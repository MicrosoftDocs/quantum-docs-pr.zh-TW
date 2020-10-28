---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699401"
---
# <a name="windows-function"></a>Windows 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


傳回長度的所有連續 subarrays `size` 。

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>描述

此函數會依 `n - size + 1` 序傳回所有長度的 subarrays `size` ，其中 `n` 是的長度 `arr` 。
第一個 subarrays 會 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直到最後一個子陣列為止 `arr[n - size..n - 1]` 。

如果為 `size <= 0` 或 `size > n` ，則會傳回空陣列。

## <a name="input"></a>輸入

### <a name="size--int"></a>大小： [Int](xref:microsoft.quantum.lang-ref.int)

Subarrays 的長度。


### <a name="array--t"></a>陣列： t []

元素的陣列。



## <a name="output--t"></a>Output： t [] []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。