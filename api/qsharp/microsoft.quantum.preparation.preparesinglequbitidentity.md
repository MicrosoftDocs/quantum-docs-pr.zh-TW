---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193619"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以充分混合狀態準備量子位。

它會藉由套用 depolarizing 通道 $ $ \begin{align} \Omega ( \rho) \mathrel{，來準備 $ \boldone/$2 狀態中的給定量子位： =} \frac {1} {4} \ sum_ {\mu \in \{ 0，1，2，3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}，\end{align} $ $ where $ \sigma \_ i $ 是 $i $ th Pauli 運算子，其中 $ \rho $ 是代表混合狀態的密度運算子。

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，其狀態會以上述方式 depolarized。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

混合狀態 $ \boldone/$2 描述將此作業套用至狀態的結果，會以隱含的方式描述這項作業中所做的隨機播放的預期值。
因此，在任何單一應用程式中，這項作業會將純狀態對應至純虛擬狀態，但它的運作方式如預期所述。
尤其是，這項作業可以在流程 tomography 中用來測量通道的 *非 unital* 元件。