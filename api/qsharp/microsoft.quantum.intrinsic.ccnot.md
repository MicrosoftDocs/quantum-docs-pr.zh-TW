---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819020"
---
# <a name="ccnot-operation"></a>CCNOT 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將雙向控制–不 (CCNOT) 閘道套用至三個量子位。

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
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