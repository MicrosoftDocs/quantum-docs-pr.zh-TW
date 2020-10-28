---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699803"
---
# <a name="r-operation"></a>R 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


針對指定的 Pauli 軸套用旋轉。

\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
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

以呼叫時 `pauli = PauliI` ，此作業會套用 *全域階段* 。 當與仿函數搭配使用時，這個階段可能很重要 `Controlled` 。