---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227517"
---
# <a name="pnormalized-function"></a>PNormalized 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


標準化 `Double` 標準中的向量 `L(p)` 。

亦即，假設陣列 $x $ 的型別 `Double[]` ，則會傳回陣列，其中所有專案都除以 $p $-標準 $ \| x \| _p $。

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>輸入

### <a name="p--double"></a>p： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$P $-標準中的指數 $p $。


### <a name="array--double"></a>陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]

陣列 $x $ $p $-標準 $ \| x _p $ 的正規化 \| 。

## <a name="see-also"></a>另請參閱

- [PNorm。](xref:Microsoft.Quantum.Math.PNorm)