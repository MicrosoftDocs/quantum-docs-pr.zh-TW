---
uid: Microsoft.Quantum.Intrinsic.T
title: T 運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699778"
---
# <a name="t-operation"></a>T 運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


將 T 閘道套用至單一量子位。

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>描述

這項作業可由單一矩陣 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模擬
\end{align}

## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

