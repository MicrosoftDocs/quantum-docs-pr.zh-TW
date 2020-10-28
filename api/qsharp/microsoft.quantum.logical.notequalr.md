---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697243"
---
# <a name="notequalr-function"></a>NotEqualR 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有在兩個輸入不相等時，才會傳回 true。

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="a--__invalidresult__"></a>答： __無效 <Result>__

要比較的第一個值。


### <a name="b--__invalidresult__"></a>b： __無效 <Result>__

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果和 `a` 不等於，則為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```