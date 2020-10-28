---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699746"
---
# <a name="equalcp-function"></a>EqualCP 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有當兩個輸入相等時，才會傳回 true。

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a>輸入

### <a name="a--complexpolar"></a>答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要比較的第一個值。


### <a name="b--complexpolar"></a>b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有當 `a` 等於時，才為 `b` 。