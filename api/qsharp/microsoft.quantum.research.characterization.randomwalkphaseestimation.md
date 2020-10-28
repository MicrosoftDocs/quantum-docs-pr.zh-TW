---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697554"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="d1d52-102">RandomWalkPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="d1d52-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="d1d52-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Characterization) ..........。</span><span class="sxs-lookup"><span data-stu-id="d1d52-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="d1d52-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1d52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1d52-105">使用隨機的逐步解說，在給定 oracle 和 eigenstate 的傳統測量結果上，使用近似的貝氏推斷，執行反復的階段估計。</span><span class="sxs-lookup"><span data-stu-id="d1d52-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="d1d52-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d1d52-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="d1d52-107">initialMean： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d1d52-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d1d52-108">初始一般之前分佈于 $ \phi $ 的平均值。</span><span class="sxs-lookup"><span data-stu-id="d1d52-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="d1d52-109">initialStdDev： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d1d52-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d1d52-110">初始一般之前分佈于 $ \phi $ 的標準差。</span><span class="sxs-lookup"><span data-stu-id="d1d52-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d1d52-111">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1d52-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1d52-112">要在最終「事後 posterior 估計中接受的度量數目。</span><span class="sxs-lookup"><span data-stu-id="d1d52-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="d1d52-113">maxMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1d52-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1d52-114">在作業被視為失敗之前所能執行的測量總數。</span><span class="sxs-lookup"><span data-stu-id="d1d52-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="d1d52-115">回溯： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1d52-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1d52-116">一致性檢查失敗時所要記住的結果數目。</span><span class="sxs-lookup"><span data-stu-id="d1d52-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="d1d52-117">oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="d1d52-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="d1d52-118">代表單一 $U $ 的作業，例如 $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $，但有未知的階段 $ \phi \in \mathbb{R} ^ + $。</span><span class="sxs-lookup"><span data-stu-id="d1d52-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="d1d52-119">targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d1d52-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d1d52-120">$U $ act 的暫存器。</span><span class="sxs-lookup"><span data-stu-id="d1d52-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="d1d52-121">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d1d52-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d1d52-122">最終的估計 $ \hat{\phi} \mathrel{： =} \expect [\phi] $，在此預期會將所有接受的資料放在「事後 posterior 上。</span><span class="sxs-lookup"><span data-stu-id="d1d52-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1d52-123">備註</span><span class="sxs-lookup"><span data-stu-id="d1d52-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="d1d52-124">反復階段估計和 Eigenstates</span><span class="sxs-lookup"><span data-stu-id="d1d52-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="d1d52-125">一般而言，輸入暫存器 `eigenstate` 不需要是 $U $ 的 eigenstate $ \ket{\phi} $，但可以是 eigenstates 的迭加。</span><span class="sxs-lookup"><span data-stu-id="d1d52-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="d1d52-126">假設輸入狀態是由 \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j} 提供，\end{align} 其中 $ \{ \Alpha \_ j \} $ 是複雜的係數，例如 $ \sum \_ j | \Alpha \_ j | ^ 2 = $1，其中 $U \ket{\phi \_ j} = \phi \_ j\ket {\ phi \_ j} $。</span><span class="sxs-lookup"><span data-stu-id="d1d52-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="d1d52-127">然後，執行反復的階段估計最後會融合到單一 eigenstate，如 [開發指南](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)中所述。</span><span class="sxs-lookup"><span data-stu-id="d1d52-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="d1d52-128">實驗設計</span><span class="sxs-lookup"><span data-stu-id="d1d52-128">Experiment Design</span></span>

<span data-ttu-id="d1d52-129">測量時間 $t $ 和反轉角度 $ \theta $ 傳遞給的物件 `oracle` ，是根據物件 *猜測啟發式* \Begin{align} \theta \sim \Pr ( \phi) ，\quad t \approx \frac {1} {\variance{\phi}}。</span><span class="sxs-lookup"><span data-stu-id="d1d52-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="d1d52-130">\end{align} 這種啟發學習法的最佳方式，是在一般之前的假設下，減少反復階段估計的預期「事後 posterior 變異數。</span><span class="sxs-lookup"><span data-stu-id="d1d52-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="d1d52-131">最優</span><span class="sxs-lookup"><span data-stu-id="d1d52-131">Optimality</span></span>

<span data-ttu-id="d1d52-132">這種作業接近階段 $ \phi $ 的最佳估算器，如使用二次遺失 $L ( \phi、\hat{\phi} ) \mathrel{： =} ( \phi-\hat{\phi} ) ^ $2。</span><span class="sxs-lookup"><span data-stu-id="d1d52-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="d1d52-133">如需反復階段估計統計資料的詳細資訊，請參閱 [貝氏階段估計](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="d1d52-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="d1d52-134">參考</span><span class="sxs-lookup"><span data-stu-id="d1d52-134">References</span></span>

- <span data-ttu-id="d1d52-135">Ferrie *et al.exe.* 2011 [doi： 10/tfx-cli](https://doi.org/10.1007/s11128-012-0407-6)， [arXiv： 1110.3067](https://arxiv.org/abs/1110.3067)。</span><span class="sxs-lookup"><span data-stu-id="d1d52-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="d1d52-136">Wiebe *et al.exe.* 2013 [doi： 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)， [arXiv： 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="d1d52-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="d1d52-137">Wiebe 和 Granade 2018 *(準備)* 。</span><span class="sxs-lookup"><span data-stu-id="d1d52-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>