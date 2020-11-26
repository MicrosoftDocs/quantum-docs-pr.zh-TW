---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206828"
---
# <a name="hy-operation"></a>HY 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將 Y 基礎類比套用至 Hadamard 轉換，以交換 Z 軸和 Y 軸。

在單一量子位上，Y Hadamard 轉換 $H _Y = S H $ 是：

\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。
\end{align}

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

應套用閘道的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [...。H](xref:Microsoft.Quantum.Intrinsic.H)