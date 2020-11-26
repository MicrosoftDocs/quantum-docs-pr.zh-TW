---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 7e090a116a63e26278b05dc7c2fda9b65ff15bae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208783"
---
# <a name="applytofirstthreequbitsca-operation"></a>ApplyToFirstThreeQubitsCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至註冊中的前三個量子位。
修飾詞 `CA` 表示作業可控制且 adjointable。

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a>op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

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