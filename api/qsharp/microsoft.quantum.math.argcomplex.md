---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211095"
---
# <a name="argcomplex-function"></a>ArgComplex 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回型別複數的階段 `Complex` 。

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>輸入

### <a name="input--complex"></a>輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

階段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。