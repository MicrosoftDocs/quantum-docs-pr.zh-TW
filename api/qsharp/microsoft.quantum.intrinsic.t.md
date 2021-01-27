---
uid: Microsoft.Quantum.Intrinsic.T
title: T 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817522"
---
# <a name="t-operation"></a>T 運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將 T 閘道套用至單一量子位。

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這項作業可由單一矩陣 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模擬
\end{align}

## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

