---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210432"
---
# <a name="prepareidentity-operation"></a>PrepareIdentity 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在指定暫存器的情況下，以充分混合狀態準備該註冊。

註冊會在 $ \boldone/2 ^ N $ 狀態中備妥，方法是將完整的 depolarizing 通道套用到每個量子位，其中 $N $ 是註冊的長度。

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要以上述方式 depolarized 其狀態的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [PrepareSingleQubitIdentity。](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)