---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698751"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

包： [](https://nuget.org/packages/)


使用單一 oracle 的整數乘冪，執行反復 (傳統方式控制) 階段估計演算法的單一反復專案。

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

以整數和暫存器為目標的作業，例如 $U ^ m $ 會套用至指定的暫存器，其中 $U $ 是要預估其階段的單一位置，而 $m $ 是指定給 oracle 的整數乘冪


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

要套用指定之單一 oracle 的次數。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

在對目標狀態採取行動之前，用來將控制項量子位上的階段反轉的角度。


### <a name="targetstate--qubit"></a>targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊指定的單一 oracle 所採取的狀態。


### <a name="controlqubit--qubit"></a>controlQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

用來控制指定 oracle 之應用程式的輔助量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

