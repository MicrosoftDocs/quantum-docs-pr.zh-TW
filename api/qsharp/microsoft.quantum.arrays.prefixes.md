---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 首碼函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699433"
---
# <a name="prefixes-function"></a>首碼函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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