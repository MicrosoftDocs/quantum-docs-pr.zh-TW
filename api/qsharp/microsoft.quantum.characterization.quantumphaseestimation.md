---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839667"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對給定的 oracle 執行量子階段估計演算法 `U` ，並將 `targetState` 該階段讀入位元組由大到小的量子暫存器中。

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

為指定的整數執行 $U ^ m $ 的作業 m。


### <a name="targetstate--qubit"></a>targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子暫存器，代表 $U $ 所採取的狀態 $ \ket{\phi} $。 如果 $ \ket{\phi} $ 是 $U $ 的 eigenstate，$U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ 表示 $ \phi \in [0，2 \ pi) $ 未知的階段。


### <a name="controlregister--bigendian"></a>controlRegister： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

以位元組由大到小的整數暫存器，可用來控制提供的 oracle，並在應用程式執行此作業後，包含 $ \phi $ 的標記法。 ControlRegister 假設是在初始狀態 $ \ket{00\cdots 0} $ 中啟動，而暫存器的長度表示所要的精確度。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

