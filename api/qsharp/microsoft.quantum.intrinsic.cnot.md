---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700338"
---
# <a name="cnot-operation"></a>CNOT 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


將受控制-不 (CNOT) 閘道套用至一對量子位。

\begin{align} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}，\end{align}

其中的資料列和資料行會依照量子概念指南中的順序排序。

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="control--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CNOT 閘道的控制項量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CNOT 閘道的目標量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
Controlled X([control], target);
```