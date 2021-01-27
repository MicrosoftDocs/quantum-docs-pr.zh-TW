---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: ComplexAsComplexPolar 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: 4d7da9b2fd79c4b39494fd1746c303a6003139eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848857"
---
# <a name="complexascomplexpolar-function"></a>ComplexAsComplexPolar 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將複數類型的複數轉換 `Complex` 成類型的複數 `ComplexPolar` 。

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a>輸入

### <a name="input--complex"></a>輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)

複數 $c = x + i y $。



## <a name="output--complexpolar"></a>輸出： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複數 $c = r e ^ {i t} $。