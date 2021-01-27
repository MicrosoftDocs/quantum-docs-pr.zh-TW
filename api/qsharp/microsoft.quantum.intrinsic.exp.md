---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819018"
---
# <a name="exp-operation"></a>Exp 運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


套用多量子位 Pauli 運算子的指數。

\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}，\end{align} where $P _i $ 是 $i $ th 的元素 `paulis` ，而 where $N = $ `Length(paulis)` 。

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

單一量子位 Pauli 值的陣列，表示每個量子位上的 tensor 產品因素。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

指定的多量子位 Pauli 運算子（目標暫存器要旋轉的角度）的角度。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊以將指定的旋轉套用至。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

