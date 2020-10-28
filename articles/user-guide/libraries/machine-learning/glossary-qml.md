---
title: 量子機器學習程式庫詞彙
description: 量子機器學習服務詞彙的詞彙
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 476e93e3737dee6ad8f3a97e8ffbcfb9b0012ee1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691522"
---
# <a name="quantum-machine-learning-glossary"></a><span data-ttu-id="52fec-103">量子 Machine Learning 詞彙</span><span class="sxs-lookup"><span data-stu-id="52fec-103">Quantum Machine Learning glossary</span></span>

<span data-ttu-id="52fec-104">以電路為中心的量子分類器定型是一種處理常式，其中包含許多需要相同 (或稍微放大) 數量的校正的程式，例如傳統分類器的定型。</span><span class="sxs-lookup"><span data-stu-id="52fec-104">Training of a circuit-centric quantum classifier is a process with many moving parts that require the same (or slightly larger) amount of calibration by trial and error as training of traditional classifiers.</span></span> <span data-ttu-id="52fec-105">我們在這裡定義了此訓練流程的主要概念和要素。</span><span class="sxs-lookup"><span data-stu-id="52fec-105">Here we define the main concepts and ingredients of this training process.</span></span>

## <a name="trainingtesting-schedules"></a><span data-ttu-id="52fec-106">定型/測試排程</span><span class="sxs-lookup"><span data-stu-id="52fec-106">Training/testing schedules</span></span>

<span data-ttu-id="52fec-107">在分類器定型的內容中， *排程* 會描述整體定型或測試集中的一部分資料樣本。</span><span class="sxs-lookup"><span data-stu-id="52fec-107">In the context of classifier training a *schedule* describes a subset of data samples in an overall training or testing set.</span></span> <span data-ttu-id="52fec-108">排程通常定義為範例索引的集合。</span><span class="sxs-lookup"><span data-stu-id="52fec-108">A schedule is usually defined as a collection of sample indices.</span></span>

## <a name="parameterbias-scores"></a><span data-ttu-id="52fec-109">參數/偏差分數</span><span class="sxs-lookup"><span data-stu-id="52fec-109">Parameter/bias scores</span></span>

<span data-ttu-id="52fec-110">假設有一個候選參數向量和分類偏差，其 *驗證分數* 會相對於所選的驗證排程來測量，並以排程 s 中所有範例的情形計數來表示。</span><span class="sxs-lookup"><span data-stu-id="52fec-110">Given a candidate parameter vector and a classifier bias, their *validation score* is measured relative to a chosen validation schedule S and is expressed by a number of misclassifications counted over all the samples in the schedule S.</span></span>

## <a name="hyperparameters"></a><span data-ttu-id="52fec-111">超參數</span><span class="sxs-lookup"><span data-stu-id="52fec-111">Hyperparameters</span></span>

<span data-ttu-id="52fec-112">模型定型程式是由稱為 *超參數* 的特定預先設定值所控制：</span><span class="sxs-lookup"><span data-stu-id="52fec-112">The model training process is governed by certain pre-set values called *hyperparameters* :</span></span>

### <a name="learning-rate"></a><span data-ttu-id="52fec-113">學習率</span><span class="sxs-lookup"><span data-stu-id="52fec-113">Learning rate</span></span>

<span data-ttu-id="52fec-114">這是其中一個關鍵超參數。</span><span class="sxs-lookup"><span data-stu-id="52fec-114">It is one of the key hyperparameters.</span></span> <span data-ttu-id="52fec-115">它會定義目前的隨機漸層估計影響參數更新的程度。</span><span class="sxs-lookup"><span data-stu-id="52fec-115">It defines how much current stochastic gradient estimate impacts the parameter update.</span></span> <span data-ttu-id="52fec-116">參數更新差異的大小與學習速率成正比。</span><span class="sxs-lookup"><span data-stu-id="52fec-116">The size of parameter update delta is proportional to the learning rate.</span></span> <span data-ttu-id="52fec-117">較小的學習率值會導致參數演進速度變慢，且聚合速度較慢，但過度大的 LR 值可能會中斷聚合，因為梯度下降永遠不會認可到特定的本機最小值。</span><span class="sxs-lookup"><span data-stu-id="52fec-117">Smaller learning rate values lead to slower parameter evolution and slower convergence, but excessively large values of LR may break the convergence altogether as the gradient descent never commits to a particular local minimum.</span></span> <span data-ttu-id="52fec-118">雖然定型演算法會以自我調整方式將學習速率調整為某個程度，但為此選取良好的初始值是很重要的。</span><span class="sxs-lookup"><span data-stu-id="52fec-118">While learning rate is adaptively adjusted by the training algorithm to some extent, selecting a good initial value for it is important.</span></span> <span data-ttu-id="52fec-119">學習速率的一般預設初始值為0.1。</span><span class="sxs-lookup"><span data-stu-id="52fec-119">A usual default initial value for learning rate is 0.1.</span></span> <span data-ttu-id="52fec-120">選取最佳的學習速率值是一種精細的 (請參閱，例如，Goodfellow 的第4.3 節。」、「深度學習」、MIT 按 2017) 。</span><span class="sxs-lookup"><span data-stu-id="52fec-120">Selecting the best value of learning rate is a fine art (see, for example, section 4.3 of Goodfellow et al.,"Deep learning", MIT Press, 2017).</span></span>

### <a name="minibatch-size"></a><span data-ttu-id="52fec-121">迷你批次大小</span><span class="sxs-lookup"><span data-stu-id="52fec-121">Minibatch size</span></span>

<span data-ttu-id="52fec-122">定義用於單一隨機漸層估計的資料樣本數。</span><span class="sxs-lookup"><span data-stu-id="52fec-122">Defines how many data samples is used for a single estimation of stochastic gradient.</span></span> <span data-ttu-id="52fec-123">迷你批次大小較大的值通常會導致更健全且更單純的聚合，但可能會減緩定型程式，因為任何一個漸層估計的成本與 minimatch 的大小成正比。</span><span class="sxs-lookup"><span data-stu-id="52fec-123">Larger values of minibatch size generally lead to more robust and more monotonic convergence but can potentially slow down the training process, as the cost of any one gradient estimation is proportional to the minimatch size.</span></span> <span data-ttu-id="52fec-124">迷你批次大小的一般預設值為10。</span><span class="sxs-lookup"><span data-stu-id="52fec-124">A usual default value for the minibatch size is 10.</span></span>

### <a name="training-epochs-tolerance-gridlocks"></a><span data-ttu-id="52fec-125">訓練 epoch、容錯、gridlocks</span><span class="sxs-lookup"><span data-stu-id="52fec-125">Training epochs, tolerance, gridlocks</span></span>

<span data-ttu-id="52fec-126">「Epoch」表示經過排程定型資料的一次完成。</span><span class="sxs-lookup"><span data-stu-id="52fec-126">"Epoch" means one complete pass through the scheduled training data.</span></span>
<span data-ttu-id="52fec-127">每個定型執行緒的 epoch 數目上限 (請參閱下面) 應該有上限。</span><span class="sxs-lookup"><span data-stu-id="52fec-127">The maximum number of epochs per a training thread (see below) should be capped.</span></span> <span data-ttu-id="52fec-128">定型執行緒的定義是使用最佳的已知候選參數來終止 (，) 在 epoch 數目上限已執行時。</span><span class="sxs-lookup"><span data-stu-id="52fec-128">The training thread is defined to terminate (with the best known candidate parameters) when the maximum number of epochs has been run.</span></span> <span data-ttu-id="52fec-129">不過，當驗證排程的分類誤判率低於選擇的容錯時，這類訓練會稍早終止。</span><span class="sxs-lookup"><span data-stu-id="52fec-129">However such training would terminate earlier when misclassification rate on validation schedule falls below a chosen tolerance.</span></span> <span data-ttu-id="52fec-130">例如，假設分類誤判容錯為 0.01 (1% ) ;如果在2000範例的驗證集上，我們看到的情形少於20個，則表示已達到容錯層級。</span><span class="sxs-lookup"><span data-stu-id="52fec-130">Suppose, for example, that misclassification tolerance is 0.01 (1%); if on validation set of 2000 samples we are seeing fewer than 20 misclassifications, then the tolerance level has been achieved.</span></span> <span data-ttu-id="52fec-131">如果候選模型的驗證分數尚未在 gridlock) 的數個連續 (epoch 中顯示任何改進，則定型執行緒也會提前終止。</span><span class="sxs-lookup"><span data-stu-id="52fec-131">A training thread also terminates prematurely if the validation score of the candidate model has not shown any improvement over several consecutive epochs (a gridlock).</span></span> <span data-ttu-id="52fec-132">Gridlock 終止的邏輯目前已硬式編碼。</span><span class="sxs-lookup"><span data-stu-id="52fec-132">The logic for the gridlock termination is currently hardcoded.</span></span>

### <a name="measurements-count"></a><span data-ttu-id="52fec-133">度量計數</span><span class="sxs-lookup"><span data-stu-id="52fec-133">Measurements count</span></span>

<span data-ttu-id="52fec-134">在量子裝置上估計定型/驗證分數和隨機漸層的元件，以預估需要適當可預見值的多個度量的量子狀態重迭。</span><span class="sxs-lookup"><span data-stu-id="52fec-134">Estimating the training/validation scores and the components of the stochastic gradient on a quantum device amounts to estimating quantum state overlaps that requires multiple measurements of the appropriate observables.</span></span> <span data-ttu-id="52fec-135">度量的數目應調整為 $O (1/\ epsilon ^ 2) $，其中 $ \epsilon $ 是所需的估計錯誤。</span><span class="sxs-lookup"><span data-stu-id="52fec-135">The number of measurements should scale as $O(1/\epsilon^2)$ where $\epsilon$ is the desired estimation error.</span></span>
<span data-ttu-id="52fec-136">根據經驗法則，初始測量計數可能大約 $ 1/\ .mbox {容錯} ^ 2 $ (查看上一個段落中的容錯定義) 。</span><span class="sxs-lookup"><span data-stu-id="52fec-136">As a rule of thumb, the initial measurements count could be approximately $1/\mbox{tolerance}^2$ (see definition of tolerance in the previous paragraph).</span></span> <span data-ttu-id="52fec-137">如果漸層下降出現太不穩定，而且聚合太難達成，則必須將測量計數向上修改一次。</span><span class="sxs-lookup"><span data-stu-id="52fec-137">One would need to revise the measurement count upward if the gradient descent appears to be too erratic and convergence too hard to achieve.</span></span>

### <a name="training-threads"></a><span data-ttu-id="52fec-138">定型執行緒</span><span class="sxs-lookup"><span data-stu-id="52fec-138">Training threads</span></span>

<span data-ttu-id="52fec-139">分類器定型公用程式的機率函數很少是凸出，這表示它在參數空間中通常會有許多本機 optima，可能會因為品質而大幅差異。</span><span class="sxs-lookup"><span data-stu-id="52fec-139">The likelihood function which is the training utility for the classifier is very seldom convex, meaning that it usually has a multitude of local optima in the parameter space that may differ significantly by quality.</span></span> <span data-ttu-id="52fec-140">因為 SGD 程式只可融合到一個特定的最佳，所以請務必流覽多個起始參數向量。</span><span class="sxs-lookup"><span data-stu-id="52fec-140">Since the SGD process can converge to only one specific optimum, it is important to explore multiple starting parameter vectors.</span></span> <span data-ttu-id="52fec-141">機器學習中的常見作法是隨機初始化這類的起始向量。</span><span class="sxs-lookup"><span data-stu-id="52fec-141">Common practice in machine learning is to initialize such starting vectors randomly.</span></span> <span data-ttu-id="52fec-142">:::no-loc(Q#):::定型 API 接受這類起始向量的任意陣列，但基礎程式碼會依序探索它們。</span><span class="sxs-lookup"><span data-stu-id="52fec-142">The :::no-loc(Q#)::: training API accepts an arbitrary array of such starting vectors but the underlying code explores them sequentially.</span></span> <span data-ttu-id="52fec-143">在多核心電腦上，或事實上在任何平行運算架構上，建議您執行數個訓練 API 的呼叫，以 :::no-loc(Q#)::: 平行地在呼叫之間進行不同的參數初始化。</span><span class="sxs-lookup"><span data-stu-id="52fec-143">On a multicore computer or in fact on any parallel computing architecture it is advisable to perform several calls to :::no-loc(Q#)::: training API in parallel with different parameter initializations across the calls.</span></span>

#### <a name="how-to-modify-the-hyperparameters"></a><span data-ttu-id="52fec-144">如何修改超參數</span><span class="sxs-lookup"><span data-stu-id="52fec-144">How to modify the hyperparameters</span></span>

<span data-ttu-id="52fec-145">在 QML 程式庫中，修改超參數的最佳方式是覆寫 UDT 的預設值 [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) 。</span><span class="sxs-lookup"><span data-stu-id="52fec-145">In the QML library, the best way to modify the hyperparameters is by overriding the default values of the UDT [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions).</span></span> <span data-ttu-id="52fec-146">若要這樣做，我們會使用函式來呼叫它 [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) ，並套用運算子 `w/` 以覆寫預設值。</span><span class="sxs-lookup"><span data-stu-id="52fec-146">To do this we call it with the function [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) and apply the operator `w/` to override the default values.</span></span> <span data-ttu-id="52fec-147">例如，若要使用100000測量和0.01 的學習率：</span><span class="sxs-lookup"><span data-stu-id="52fec-147">For example, to use 100,000 measurements and a learning rate of 0.01:</span></span>

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
