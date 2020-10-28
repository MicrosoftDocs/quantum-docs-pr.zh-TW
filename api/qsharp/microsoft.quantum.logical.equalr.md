---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697311"
---
# <a name="equalr-function"></a>EqualR 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有當兩個輸入相等時，才會傳回 true。

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="a--__invalidresult__"></a>答： __無效 <Result>__

要比較的第一個值。


### <a name="b--__invalidresult__"></a>b： __無效 <Result>__

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有當 `a` 等於時，才為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```