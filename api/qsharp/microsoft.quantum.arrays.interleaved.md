---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交錯函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220955"
---
# <a name="interleaved-function"></a>交錯函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


交錯 (的兩個數組幾乎) 相同大小。

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>描述

此函式會傳回兩個數組的交錯，從第一個陣列中的第一個元素開始，然後是第二個數組中的第一個元素，依此類推。

第一個陣列的長度必須與第二個數組的長度相同，或者可以有一個以上的元素。

## <a name="input"></a>輸入

### <a name="first--t"></a>first： t []

要交錯的第一個陣列。


### <a name="second--t"></a>second： t []

要交錯的第二個數組。



## <a name="output--t"></a>Output： t []

交錯陣列

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

和之每個元素的型別 `first` `second` 。