---
uid: Microsoft.Quantum.Intrinsic.M
title: M 運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699806"
---
# <a name="m-operation"></a>M 運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


以 Pauli $Z $ 基礎來測量單一量子位。

輸出結果是由散發 \begin{align} \Pr ( \texttt{Zero} 所提供 |\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要測量的量子位。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__

`Zero` 如果觀察到 $ + $1 eigenvalue，以及 `One` 是否觀察到 $-$1 eigenvalue。

## <a name="remarks"></a>備註

相當於：

```qsharp
Measure([PauliZ], [qubit]);
```