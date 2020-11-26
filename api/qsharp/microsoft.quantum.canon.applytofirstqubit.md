---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 851f2b58a914c8b09188f442e442b91a8ede5416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217487"
---
# <a name="applytofirstqubit-operation"></a>ApplyToFirstQubit 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至註冊中的第一個量子位。

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要套用至第一個量子位的作業


### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位陣列至套用作業的第一個量子位



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. ApplyToFirstQubitA](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [Canon. ApplyToFirstQubitC](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [Canon. ApplyToFirstQubitCA](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)