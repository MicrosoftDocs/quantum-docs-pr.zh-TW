---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交錯函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848104"
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

## <a name="example"></a>範例

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```