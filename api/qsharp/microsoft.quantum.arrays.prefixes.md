---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 首碼函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220379"
---
# <a name="prefixes-function"></a>首碼函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定陣列時，會傳回其所有前置詞。

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>描述

傳回所有前置詞的陣列，開頭為只有第一個元素才是完整陣列的陣列。

## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t []

元素的陣列。



## <a name="output--t"></a>Output： t [] []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

元素的類型 `array` 。