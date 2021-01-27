---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848363"
---
# <a name="expmodl-function"></a>ExpModL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對給定的模數，傳回引發至給定乘冪的整數。

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>描述

讓我們以 $x $、乘 $p $ 和模數 $N $ 來表示 expBase。
函數會傳回 $x ^ p \operatorname{mod} N $。

我們假設 $N $、$x $ 為正面且電源為非負數。

## <a name="input"></a>輸入

### <a name="expbase--bigint"></a>expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>備註

花費的時間與中的位數成正比 `power` ，而不是本身的位數 `power` 。