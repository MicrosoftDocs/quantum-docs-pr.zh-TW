---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211384"
---
# <a name="abscomplex-function"></a>AbsComplex 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回型別複數的絕對值 `Complex` 。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>輸入

### <a name="input--complex"></a>輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

絕對值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。