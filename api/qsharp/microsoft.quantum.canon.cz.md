---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699045"
---
# <a name="cz-operation"></a>CZ 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將控制的 Z (CZ) 閘道套用至一對量子位。

$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中資料列和資料行的組織方式如量子概念指南中所示。

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="control--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CZ 閘道的控制項量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CZ 閘道的目標量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
Controlled Z([control], target);
```