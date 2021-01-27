---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851809"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對給定的 oracle 和 eigenstate 執行健全的非反復式量子階段估計演算法 `U` ，並提供以海森堡限制的變異數調整之階段的單一實際值估計。

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>輸入

### <a name="bitsprecision--int"></a>bitsPrecision： [Int](xref:microsoft.quantum.lang-ref.int)

這會提供 $ \phi $ with 標準差 $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ 的估計值，並使用許多查詢規模調整，例如 $ \sigma \le 10.7 \pi/\text{的查詢數} $。


### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

為指定的整數 $U ^ m $ 執行運算的作業 $m $。


### <a name="targetstate--qubit"></a>targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ 作用的量子暫存器。 如果它儲存 $U $ 的 eigenstate $ \ket{\phi} $，則 $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ 表示 $ \phi\in (-\pi，\pi] $ 未知的階段。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>備註

在大量查詢的限制中，Cramer-Rao 預估 $ \phi $ 滿足 $ \sigma \ge 2 \pi/\text{的查詢數} $ 的標準差下限。

## <a name="references"></a>參考資料

- 透過健全的階段估計 Shelby Kimmel、Guang Hao Low、Theodore dreiser 所 J. Yoder，穩固的通用 Single-Qubit Gate-Set 的校正 https://arxiv.org/abs/1502.02677