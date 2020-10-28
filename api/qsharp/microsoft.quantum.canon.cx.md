---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699049"
---
# <a name="cx-operation"></a>CX 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將受控制 X (CX) 閘道套用至一對量子位。

$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中資料列和資料行的組織方式與量子概念指南中的組織方式相同。

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="control--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)

適用于 CX 閘道的控制量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CX 閘道的目標量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
Controlled X([control], target);
```

以及：

```qsharp
CNOT(control, target);
```