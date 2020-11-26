---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210466"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


成對 entangles 兩個量子位暫存器。

亦即，假設有兩個暫存器，請在個別暫存器上的每一對 \left 之間準備充分纏結 state $ \frac {1} {\sqrt {2} } \ket ( \ket {00} + \right {11} 量子位) $，假設每個暫存器都是以 $ \ket{0\cdots 0} $ 狀態開始。

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="left--qubit"></a>左方： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 狀態中的量子位陣列


### <a name="right--qubit"></a>right： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 狀態中的量子位陣列



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

