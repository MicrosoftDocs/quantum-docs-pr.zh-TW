---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826197"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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