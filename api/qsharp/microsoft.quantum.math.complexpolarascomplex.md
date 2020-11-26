---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: ace458ec168b70a873fae2a4990b9a427efac7cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228605"
---
# <a name="complexpolarascomplex-function"></a>ComplexPolarAsComplex 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將複數類型的複數轉換 `ComplexPolar` 成類型的複數 `Complex` 。

```qsharp
function ComplexPolarAsComplex (input : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a>輸入

### <a name="input--complexpolar"></a>輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複數 $c = r e ^ {i t} $。



## <a name="output--complex"></a>輸出： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。