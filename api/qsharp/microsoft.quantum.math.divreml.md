---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 40ce295b82d138ad0b5261641c7f3649631d309d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210840"
---
# <a name="divreml-function"></a>DivRemL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將一個 BigInteger 值除以另一個值，並以元組傳回結果和餘數。

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>輸入

### <a name="dividend--bigint"></a>被除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="divisor--bigint"></a>除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigintbigint"></a>輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) 



## <a name="remarks"></a>備註

如需詳細資訊，請參閱 [BigInteger. DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) 。