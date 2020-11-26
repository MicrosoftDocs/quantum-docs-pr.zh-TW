---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214002"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


建立 `arr` 由 start 列舉的整數陣列。步。。結束。

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>輸入

### <a name="range--range"></a>範圍： [範圍](xref:microsoft.quantum.lang-ref.range)

`Range` `start..step..end` 要轉換為數組的值的。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

新的整數陣列，對應至逐一查看的值 `range` 。