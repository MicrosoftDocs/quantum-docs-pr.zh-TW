---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699794"
---
# <a name="r1frac-operation"></a>R1Frac 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


{1}以指定為 dyadic 分數的角度，套用有關 $ \ket $ 狀態的旋轉。

\begin{align} R_1 (n，k) \mathrel{： =} \operatorname{diag} (1，e ^ {i \pi k/2 ^ n} ) 。
\end{align}

> [!WARNING]
> 這項作業會使用與 **相反** 的正負號慣例 @"microsoft.quantum.intrinsic.r" ，而不包含包含的 $ 1/2 $ 的因素 @"microsoft.quantum.intrinsic.r1" 。

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

Dyadic 分數中的分子，用來旋轉量子位的角度。


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

二的乘冪，指定量子位旋轉的角度的分母。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```