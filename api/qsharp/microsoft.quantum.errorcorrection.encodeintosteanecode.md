---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697986"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


一種編碼作業，會將未編碼的量子暫存器對應至⟦7、1、3⟧ Steane 量副程式代碼底下的編碼量子暫存器。

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>輸入

### <a name="physregister--qubit"></a>physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

保存未編碼之量子狀態的量子位暫存器


### <a name="auxqubits--qubit"></a>auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位暫存器，其一開始是零，並會新增至量子系統，以便執行編碼作業



## <a name="output--logicalregister"></a>輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

在套用 Steane 編碼器之後保留狀態的量子註冊程式

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)