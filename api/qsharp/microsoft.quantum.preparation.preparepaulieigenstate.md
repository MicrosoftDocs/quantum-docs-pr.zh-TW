---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854348"
---
# <a name="preparepaulieigenstate-operation"></a>PreparePauliEigenstate 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


準備指定 Pauli 運算子的正 eigenstate 中的量子位。
如果指定了識別運算子，則會以充分混合狀態準備量子位。

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>描述

如果量子位一開始是 $ \ket {0} $ 狀態，則此作業會準備指定 Pauli 操作員的 $ + $1 eigenstate 中的量子位，或者，若為 `PauliI` ，則改為在充分混合狀態中 (查看 <xref:microsoft.quantum.preparation.preparesinglequbitidentity>) 。

如果量子位的狀態不是 $ \ket {0} $，這項作業會套用下列閘道： $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` 和 <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` 。

## <a name="input"></a>輸入

### <a name="basis--pauli"></a>基礎： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 運算子 $P $。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要準備的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

若要準備 $ \ket{+} $ 狀態中的量子位：

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```