---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697727"
---
# <a name="expfrac-operation"></a>ExpFrac 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


以 dyadic 分數指定的引數，套用多量子位 Pauli 運算子的指數。

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}，\end{align} where $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

單一量子位 Pauli 值的陣列，表示每個量子位上的 tensor 產品因素。


### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

分子 ($k $) 以 dyadic 分數表示量子位暫存器要旋轉的角度。


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

兩個 (的乘冪 $n $) 指定量子位註冊要旋轉的角度的分母。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊以將指定的旋轉套用至。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

