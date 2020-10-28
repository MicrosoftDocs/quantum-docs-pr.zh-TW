---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交錯函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699467"
---
# <a name="interleaved-function"></a>交錯函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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