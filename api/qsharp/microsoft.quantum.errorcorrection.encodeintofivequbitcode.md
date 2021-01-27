---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826312"
---
# <a name="encodeintofivequbitcode-operation"></a>EncodeIntoFiveQubitCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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