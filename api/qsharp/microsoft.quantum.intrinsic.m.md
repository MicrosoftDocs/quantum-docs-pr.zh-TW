---
uid: Microsoft.Quantum.Intrinsic.M
title: M 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818882"
---
# <a name="m-operation"></a>M 運算

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


以 Pauli $Z $ 基礎來測量單一量子位。

輸出結果是由散發 \begin{align} \Pr ( \texttt{Zero} 所提供 |\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要測量的量子位。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

`Zero` 如果觀察到 $ + $1 eigenvalue，以及 `One` 是否觀察到 $-$1 eigenvalue。

## <a name="remarks"></a>備註

相當於：

```qsharp
Measure([PauliZ], [qubit]);
```