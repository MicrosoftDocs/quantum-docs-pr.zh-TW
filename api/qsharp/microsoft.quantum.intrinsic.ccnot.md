---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697742"
---
# <a name="ccnot-operation"></a>CCNOT 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


將雙向控制–不 (CCNOT) 閘道套用至三個量子位。

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="control1--qubit"></a>control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CCNOT 閘道的第一個控制量子位。


### <a name="control2--qubit"></a>control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CCNOT 閘道的第二個控制項量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

CCNOT 閘道的目標量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相當於：

```qsharp
Controlled X([control1, control2], target);
```