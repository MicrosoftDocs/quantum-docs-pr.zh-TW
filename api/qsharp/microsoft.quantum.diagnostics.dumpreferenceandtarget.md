---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698118"
---
# <a name="dumpreferenceandtarget-operation"></a>DumpReferenceAndTarget 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


使用 DumpRegister 來提供參考和目標暫存器狀態的診斷。 撰寫為個別的作業，以允許將覆寫和解讀為個別的暫存器，而不是單一組合的暫存器。

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="reference--qubit"></a>參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

