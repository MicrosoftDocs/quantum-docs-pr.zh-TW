---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701010"
---
# <a name="squarednorm-function"></a>SquaredNorm 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回向量的平方二標準。

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>描述

傳回向量的平方二標準;亦即，假設輸入 $ \vec{x} $，則會傳回 $ \ sum_i x_i ^ 2 $。

## <a name="input"></a>輸入

### <a name="array--double"></a>陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]

要傳回其平方2標準的向量。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

的平方雙標準 `array` 。