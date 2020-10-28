---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700231"
---
# <a name="pnorm-function"></a>PNorm 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回 `L(p)` 向量的標準 `Double` 。

亦即，假設陣列 $x $ 的型 `Double[]` 別，這會傳回 $p $-標準 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>輸入

### <a name="p--double"></a>p： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$P $-標準中的指數 $p $。


### <a name="array--double"></a>陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$P $-標準 $ \| x \| _p $。