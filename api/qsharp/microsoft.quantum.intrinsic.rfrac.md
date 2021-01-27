---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: c80bb2b394e83c1133ed6ddc1640a3d88563ca6e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818491"
---
# <a name="rfrac-operation"></a>RFrac 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


使用指定為 dyadic 分數的角度，對指定的 Pauli 軸套用旋轉。

\begin{align} R_ {\mu} (n，k) \mathrel{： =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。

> [!WARNING]
> 這種作業會使用與 **相反** 的正負號慣例 @"microsoft.quantum.intrinsic.r" 。

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要 exponentiated 以形成旋轉的 Pauli 運算子。


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
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```