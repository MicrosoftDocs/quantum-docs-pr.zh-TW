---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b26ad3515cb801b122858b9474aea76a0e5c498b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697251"
---
# <a name="notequalc-function"></a>NotEqualC 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有在兩個輸入不相等時，才會傳回 true。

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a>輸入

### <a name="a--complex"></a>a： [複雜](xref:Microsoft.Quantum.Math.Complex)

要比較的第一個值。


### <a name="b--complex"></a>b： [複雜](xref:Microsoft.Quantum.Math.Complex)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果和 `a` 不等於，則為 `b` 。