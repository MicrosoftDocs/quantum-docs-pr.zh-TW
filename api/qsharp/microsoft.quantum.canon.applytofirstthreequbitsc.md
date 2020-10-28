---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699192"
---
# <a name="applytofirstthreequbitsc-operation"></a>ApplyToFirstThreeQubitsC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將作業套用至註冊中的前三個量子位。
修飾詞 `C` 表示作業可控制。

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubitqubitqubit--unit-ctl"></a>op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要套用至前三個量子位的作業


### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位陣列至套用作業的前三個量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這相當於：

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)