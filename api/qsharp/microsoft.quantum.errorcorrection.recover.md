---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 復原操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825513"
---
# <a name="recover-operation"></a>復原操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


依類型所描述的量副程式代碼，執行單次錯誤修正 `QECC` 。

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>輸入

### <a name="code--qecc"></a>程式碼： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

封裝為類型的量子錯誤修正程式碼 `QECC` 會描述量子資料的編碼和解碼，以及如何測量錯誤 syndromes。


### <a name="fn--recoveryfn"></a>fn： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`，會將每個錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定義了穩定程式碼的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)