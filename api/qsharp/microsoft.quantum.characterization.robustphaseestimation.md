---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216076"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="a4a6d-102">RobustPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="a4a6d-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="a4a6d-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="a4a6d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="a4a6d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4a6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4a6d-105">針對給定的 oracle 和 eigenstate 執行健全的非反復式量子階段估計演算法 `U` ，並提供以海森堡限制的變異數調整之階段的單一實際值估計。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="a4a6d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a4a6d-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="a4a6d-107">bitsPrecision： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4a6d-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a4a6d-108">這會提供 $ \phi $ with 標準差 $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ 的估計值，並使用許多查詢規模調整，例如 $ \sigma \le 10.7 \pi/\text{的查詢數} $。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="a4a6d-109">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="a4a6d-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="a4a6d-110">為指定的整數 $U ^ m $ 執行運算的作業 $m $。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="a4a6d-111">targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a4a6d-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a4a6d-112">$U $ 作用的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="a4a6d-113">如果它儲存 $U $ 的 eigenstate $ \ket{\phi} $，則 $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ 表示 $ \phi\in (-\pi，\pi] $ 未知的階段。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="a4a6d-114">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a4a6d-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4a6d-115">備註</span><span class="sxs-lookup"><span data-stu-id="a4a6d-115">Remarks</span></span>

<span data-ttu-id="a4a6d-116">在大量查詢的限制中，Cramer-Rao 預估 $ \phi $ 滿足 $ \sigma \ge 2 \pi/\text{的查詢數} $ 的標準差下限。</span><span class="sxs-lookup"><span data-stu-id="a4a6d-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="a4a6d-117">參考</span><span class="sxs-lookup"><span data-stu-id="a4a6d-117">References</span></span>

- <span data-ttu-id="a4a6d-118">透過健全的階段估計 Shelby Kimmel、Guang Hao Low、Theodore dreiser 所 J. Yoder，穩固的通用 Single-Qubit Gate-Set 的校正 https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="a4a6d-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>