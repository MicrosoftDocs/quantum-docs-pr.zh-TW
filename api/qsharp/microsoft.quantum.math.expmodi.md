---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857042"
---
# <a name="expmodi-function"></a>ExpModI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對給定的模數，傳回引發至給定乘冪的整數。

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>描述

讓我們以 $x $、乘 $p $ 和模數 $N $ 來表示 expBase。
函數會傳回 $x ^ p \operatorname{mod} N $。

我們假設 $N $、$x $ 為正面且電源為非負數。

## <a name="input"></a>輸入

### <a name="expbase--int"></a>expBase： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>備註

花費的時間與中的位數成正比 `power` ，而不是本身的位數 `power` 。