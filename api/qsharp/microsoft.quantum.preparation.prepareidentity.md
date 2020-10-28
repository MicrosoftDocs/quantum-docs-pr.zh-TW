---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700971"
---
# <a name="prepareidentity-operation"></a>PrepareIdentity 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


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