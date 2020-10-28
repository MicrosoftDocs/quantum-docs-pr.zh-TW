---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimateEnergyWithAdiabaticEvolution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 3fdbdd83b784cdc560e3160151fdf4ba4e7115e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700163"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a>EstimateEnergyWithAdiabaticEvolution 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


藉由在自動設定的 `statePrepUnitary` 輸入狀態上套用，然後使用來 adiabatic 狀態準備， `adiabaticUnitary` 最後針對 `qpeUnitary` 使用的結果狀態，來執行狀態準備 `phaseEstAlgorithm` 。

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

用於模擬的量子位數目。


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

代表初始 dynamical 產生器之狀態準備的 oracle。


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

代表 adiabatic 演進演算法的 oracle，此演算法會用來將掃量視為演算法的最終狀態。


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

Oracle 代表單一運算子 $U $ 代表時間 $ \delta t $ 在 dynamical 產生器下的時間 $ \ket{\phi} $ 和地面狀態能源 $E = \phi \\ ，\delta t $。


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double) 

在指定的單一作業上執行階段估計的作業。
如需詳細資訊，請參閱 [反復的階段估計](/quantum/libraries/characterization#iterative-phase-estimation) 。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

由 $U $ 所代表之產生器的接地 $ \hat{\phi} $ \phi $。