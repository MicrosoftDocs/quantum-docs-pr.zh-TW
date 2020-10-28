---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700507"
---
# <a name="argcomplex-function"></a>ArgComplex 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回型別複數的階段 `Complex` 。

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>輸入

### <a name="input--complex"></a>輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

階段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。