---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851899"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用單一 oracle 的任意實數，執行反復 (傳統方式控制) 階段估計演算法的單一反復專案。

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="oracle--continuousoracle"></a>oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

作業會在雙 $t $ 和暫存器上運作，因此 $U ^ t $ 會套用至指定的暫存器，其中 $U $ 是要預估其階段的單一位置，而 $t $ 是指定給 oracle 的整數乘冪


### <a name="time--double"></a>時間： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

要套用指定之單一 oracle 的次數。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

在對目標狀態採取行動之前，用來將控制項量子位上的階段反轉的角度。


### <a name="targetstate--qubit"></a>targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊指定的單一 oracle 所採取的狀態。


### <a name="controlqubit--qubit"></a>controlQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

