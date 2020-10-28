---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699799"
---
# <a name="r1-operation"></a>R1 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


根據指定的角度，套用大約 $ \ket {1} $ 狀態的旋轉。

\begin{align} R_1 ( \theta) \mathrel{： =} \operatorname{diag} (1，e ^ {i\theta} ) 。
\end{align}

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

要旋轉量子位的角度。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```