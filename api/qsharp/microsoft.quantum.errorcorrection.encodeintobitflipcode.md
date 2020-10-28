---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697990"
---
# <a name="encodeintobitflipcode-operation"></a>EncodeIntoBitFlipCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


編碼為 [3，1，3]/⟦3，1，1⟧位-翻轉程式碼。

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>輸入

### <a name="physregister--qubit"></a>physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

代表要保護之資料的實體量子位註冊。


### <a name="auxqubits--qubit"></a>auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

一開始會在 $ \ket $ 狀態中註冊輔助量子位， {00} 以用於編碼要保護的資料。



## <a name="output--logicalregister"></a>輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

用於編碼的實體和輔助量子位，以邏輯暫存器表示。

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)