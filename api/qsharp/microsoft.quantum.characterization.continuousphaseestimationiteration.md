---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216280"
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

