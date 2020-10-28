---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700686"
---
# <a name="abscomplex-function"></a>AbsComplex 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回型別複數的絕對值 `Complex` 。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>輸入

### <a name="input--complex"></a>輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

絕對值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。