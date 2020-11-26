---
uid: Microsoft.Quantum.Intrinsic.Measure
title: 測量運算
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212285"
---
# <a name="measure-operation"></a>測量運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


在指定的 Pauli 基底中，執行一或多個量子位的聯合度量。

輸出結果是由散發： \begin{align} \Pr ( \texttt{Zero} 所提供的：\ket{\psi} ) = \frac12 \braket{\psi \mid | \left ( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1-1} \right) \mid | \psi}、\end{align}，其中 $P _i $ 是的 $i $ 第一個元素 `bases` ，其中 $N = \texttt{Length} ( \texttt{bases} ) $。
也就是說，測量會傳回 `Result` $d $，讓觀察到的測量效果 eigenvalue 為 $ (-1) ^ d $。

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>輸入

### <a name="bases--pauli"></a>基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

單一量子位 Pauli 值的陣列，表示每個量子位上的 tensor 產品因素。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊要測量的量子位。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

`Zero` 如果觀察到 $ + $1 eigenvalue，以及 `One` 是否觀察到 $-$1 eigenvalue。

## <a name="remarks"></a>備註

如果基礎陣列和量子位陣列的長度不同，則作業將會失敗。