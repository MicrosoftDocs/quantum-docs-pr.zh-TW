---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817524"
---
# <a name="s-operation"></a>S 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將 S 閘道套用至單一量子位。

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這項作業可由單一矩陣 \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}。
\end{align}

## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

