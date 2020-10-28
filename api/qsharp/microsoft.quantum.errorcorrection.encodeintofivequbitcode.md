---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697987"
---
# <a name="encodeintofivequbitcode-operation"></a>EncodeIntoFiveQubitCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


編碼為⟦5，1，3⟧量副程式代碼。

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>輸入

### <a name="physregister--qubit"></a>physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位，代表未編碼的狀態。 這個陣列 `Qubit[]` 的長度為1。


### <a name="auxqubits--qubit"></a>auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

將用來表示已編碼狀態的輔助量子位的註冊。



## <a name="output--logicalregister"></a>輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

儲存編碼狀態之類型的實體量子位陣列 `LogicalRegister` 。

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)