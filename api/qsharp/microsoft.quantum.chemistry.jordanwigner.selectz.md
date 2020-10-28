---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698386"
---
# <a name="selectz-operation"></a>SelectZ 操作

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


單一 $U $，適用于量子位上的 Pauli $Z $ 閘道 $p $ \ket{p} $。 亦即 $ $ \begin{align} U\ket {p} \ ket {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

此註冊的狀態 $ \ket{p} $ 會決定套用 $Z $ 的量子位。


### <a name="targetregister--qubit"></a>targetRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊已套用 Pauli 運算子的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

