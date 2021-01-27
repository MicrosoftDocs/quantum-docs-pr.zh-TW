---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 329f4d0bc21e74ab6c138af39c88cdcd964e63cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857096"
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