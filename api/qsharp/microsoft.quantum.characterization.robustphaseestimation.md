---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698714"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

包： [](https://nuget.org/packages/)


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

## <a name="references"></a>參考

- 透過健全的階段估計 Shelby Kimmel、Guang Hao Low、Theodore dreiser 所 J. Yoder，穩固的通用 Single-Qubit Gate-Set 的校正 https://arxiv.org/abs/1502.02677