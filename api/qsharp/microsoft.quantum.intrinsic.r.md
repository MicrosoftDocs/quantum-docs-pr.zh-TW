---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818725"
---
# <a name="r-operation"></a>R 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


針對指定的 Pauli 軸套用旋轉。

\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 運算子 ($ \mu $) 要 exponentiated 以形成旋轉。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

要旋轉量子位的角度。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

以呼叫時 `pauli = PauliI` ，此作業會套用 *全域階段*。 當與仿函數搭配使用時，這個階段可能很重要 `Controlled` 。