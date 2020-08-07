---
title: 量子機器學習程式庫
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 52c3f69fb99384270a27e57c4f32212d18bee1a4
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868894"
---
# <a name="quantum-machine-learning-glossary"></a><span data-ttu-id="81595-102">量子 Machine Learning 詞彙</span><span class="sxs-lookup"><span data-stu-id="81595-102">Quantum Machine Learning glossary</span></span>

<span data-ttu-id="81595-103">以電路為中心的配量分類器的定型是一種程式，其中有許多移動元件需要相同的 (或稍微大一點的) 校正校準，而錯誤則是傳統分類器的定型。</span><span class="sxs-lookup"><span data-stu-id="81595-103">Training of a circuit-centric quantum classifier is a process with many moving parts that require the same (or slightly larger) amount of calibration by trial and error as training of traditional classifiers.</span></span> <span data-ttu-id="81595-104">我們將在此定義此訓練程式的主要概念和要素。</span><span class="sxs-lookup"><span data-stu-id="81595-104">Here we define the main concepts and ingredients of this training process.</span></span>

## <a name="trainingtesting-schedules"></a><span data-ttu-id="81595-105">訓練/測試排程</span><span class="sxs-lookup"><span data-stu-id="81595-105">Training/testing schedules</span></span>

<span data-ttu-id="81595-106">在分類器定型*排程*的內容中，會描述整體訓練或測試集中的資料樣本子集。</span><span class="sxs-lookup"><span data-stu-id="81595-106">In the context of classifier training a *schedule* describes a subset of data samples in an overall training or testing set.</span></span> <span data-ttu-id="81595-107">排程通常會定義為範例索引的集合。</span><span class="sxs-lookup"><span data-stu-id="81595-107">A schedule is usually defined as a collection of sample indices.</span></span>

## <a name="parameterbias-scores"></a><span data-ttu-id="81595-108">參數/偏差分數</span><span class="sxs-lookup"><span data-stu-id="81595-108">Parameter/bias scores</span></span>

<span data-ttu-id="81595-109">假設有候選參數向量和分類偏差，其*驗證分數*會相對於所選的驗證排程來測量，並以排程中所有樣本上的數個 misclassifications 表示。</span><span class="sxs-lookup"><span data-stu-id="81595-109">Given a candidate parameter vector and a classifier bias, their *validation score* is measured relative to a chosen validation schedule S and is expressed by a number of misclassifications counted over all the samples in the schedule S.</span></span>

## <a name="hyperparameters"></a><span data-ttu-id="81595-110">超參數</span><span class="sxs-lookup"><span data-stu-id="81595-110">Hyperparameters</span></span>

<span data-ttu-id="81595-111">模型定型程式是由稱為*超參數*的特定預先設定值所控制：</span><span class="sxs-lookup"><span data-stu-id="81595-111">The model training process is governed by certain pre-set values called *hyperparameters*:</span></span>

### <a name="learning-rate"></a><span data-ttu-id="81595-112">學習率</span><span class="sxs-lookup"><span data-stu-id="81595-112">Learning rate</span></span>

<span data-ttu-id="81595-113">它是其中一個重要的超參數。</span><span class="sxs-lookup"><span data-stu-id="81595-113">It is one of the key hyperparameters.</span></span> <span data-ttu-id="81595-114">它會定義目前的隨機漸層估計會對參數更新造成多少影響。</span><span class="sxs-lookup"><span data-stu-id="81595-114">It defines how much current stochastic gradient estimate impacts the parameter update.</span></span> <span data-ttu-id="81595-115">參數更新差異的大小與學習速率成正比。</span><span class="sxs-lookup"><span data-stu-id="81595-115">The size of parameter update delta is proportional to the learning rate.</span></span> <span data-ttu-id="81595-116">較小的學習速率值會導致較慢的參數進化和較慢的聚合，但過度大的 LR 值可能會中斷聚合，因為梯度下降永遠不會認可到特定的本機最小數目。</span><span class="sxs-lookup"><span data-stu-id="81595-116">Smaller learning rate values lead to slower parameter evolution and slower convergence, but excessively large values of LR may break the convergence altogether as the gradient descent never commits to a particular local minimum.</span></span> <span data-ttu-id="81595-117">雖然學習速率是由定型演算法在某種程度上進行自我調整調整，但為其選取一個良好的初始值非常重要。</span><span class="sxs-lookup"><span data-stu-id="81595-117">While learning rate is adaptively adjusted by the training algorithm to some extent, selecting a good initial value for it is important.</span></span> <span data-ttu-id="81595-118">學習速率的一般預設初始值為0.1。</span><span class="sxs-lookup"><span data-stu-id="81595-118">A usual default initial value for learning rate is 0.1.</span></span> <span data-ttu-id="81595-119">選取最佳的學習速率值是一個不錯的 (，例如，Goodfellow et al 的第4.3 節，「深度學習」，MIT 按下 2017) 。</span><span class="sxs-lookup"><span data-stu-id="81595-119">Selecting the best value of learning rate is a fine art (see, for example, section 4.3 of Goodfellow et al.,"Deep learning", MIT Press, 2017).</span></span>

### <a name="minibatch-size"></a><span data-ttu-id="81595-120">迷你批次大小</span><span class="sxs-lookup"><span data-stu-id="81595-120">Minibatch size</span></span>

<span data-ttu-id="81595-121">定義隨機漸層的單一估計使用多少資料樣本。</span><span class="sxs-lookup"><span data-stu-id="81595-121">Defines how many data samples is used for a single estimation of stochastic gradient.</span></span> <span data-ttu-id="81595-122">較大的迷你批次大小值通常會導致更強大且更單純的聚合，但可能會使定型程式變慢，因為任何一個漸層估計的成本會與 minimatch 大小成正比。</span><span class="sxs-lookup"><span data-stu-id="81595-122">Larger values of minibatch size generally lead to more robust and more monotonic convergence but can potentially slow down the training process, as the cost of any one gradient estimation is proportional to the minimatch size.</span></span> <span data-ttu-id="81595-123">迷你批次大小的一般預設值是10。</span><span class="sxs-lookup"><span data-stu-id="81595-123">A usual default value for the minibatch size is 10.</span></span>

### <a name="training-epochs-tolerance-gridlocks"></a><span data-ttu-id="81595-124">訓練 epoch、容錯、gridlocks</span><span class="sxs-lookup"><span data-stu-id="81595-124">Training epochs, tolerance, gridlocks</span></span>

<span data-ttu-id="81595-125">「Epoch」表示一次完成排程的定型資料。</span><span class="sxs-lookup"><span data-stu-id="81595-125">"Epoch" means one complete pass through the scheduled training data.</span></span>
<span data-ttu-id="81595-126">每個定型執行緒的 epoch 數目上限 (見下面) 應為上限。</span><span class="sxs-lookup"><span data-stu-id="81595-126">The maximum number of epochs per a training thread (see below) should be capped.</span></span> <span data-ttu-id="81595-127">定型執行緒定義為在執行最大 epoch 數目時，終止具有最佳已知候選參數) 的 (。</span><span class="sxs-lookup"><span data-stu-id="81595-127">The training thread is defined to terminate (with the best known candidate parameters) when the maximum number of epochs has been executed.</span></span> <span data-ttu-id="81595-128">不過，當驗證排程的分類誤判速率低於所選的容錯時，這類訓練會提早終止。</span><span class="sxs-lookup"><span data-stu-id="81595-128">However such training would terminate earlier when misclassification rate on validation schedule falls below a chosen tolerance.</span></span> <span data-ttu-id="81595-129">例如，假設分類誤判容錯為 0.01 (1% ) ;如果在2000樣本的驗證集上看到的 misclassifications 少於20個，則已達到容錯等級。</span><span class="sxs-lookup"><span data-stu-id="81595-129">Suppose, for example, that misclassification tolerance is 0.01 (1%); if on validation set of 2000 samples we are seeing fewer than 20 misclassifications, then the tolerance level has been achieved.</span></span> <span data-ttu-id="81595-130">如果候選模型的驗證分數尚未顯示 (gridlock) 之數個連續 epoch 的任何改善，訓練執行緒也會提前終止。</span><span class="sxs-lookup"><span data-stu-id="81595-130">A training thread also terminates prematurely if the validation score of the candidate model has not shown any improvement over several consecutive epochs (a gridlock).</span></span> <span data-ttu-id="81595-131">Gridlock 終止的邏輯目前已硬式編碼。</span><span class="sxs-lookup"><span data-stu-id="81595-131">The logic for the gridlock termination is currently hardcoded.</span></span>

### <a name="measurements-count"></a><span data-ttu-id="81595-132">測量計數</span><span class="sxs-lookup"><span data-stu-id="81595-132">Measurements count</span></span>

<span data-ttu-id="81595-133">在配量裝置數量上預估訓練/驗證分數和隨機漸層的元件，以估計需要多次測量適當可預見值的量子狀態重迭。</span><span class="sxs-lookup"><span data-stu-id="81595-133">Estimating the training/validation scores and the components of the stochastic gradient on a quantum device amounts to estimating quantum state overlaps that requires multiple measurements of the appropriate observables.</span></span> <span data-ttu-id="81595-134">量值的數目應該調整為 $O (1/\ epsilon ^ 2) $，其中 $ \epsilon $ 是所需的估計錯誤。</span><span class="sxs-lookup"><span data-stu-id="81595-134">The number of measurements should scale as $O(1/\epsilon^2)$ where $\epsilon$ is the desired estimation error.</span></span>
<span data-ttu-id="81595-135">根據經驗法則，初始量測計可能大約是 $ 1/\ .mbox {容錯} ^ 2 $ (請參閱上一個段落) 中的容錯定義。</span><span class="sxs-lookup"><span data-stu-id="81595-135">As a rule of thumb, the initial measurements count could be approximately $1/\mbox{tolerance}^2$ (see definition of tolerance in the previous paragraph).</span></span> <span data-ttu-id="81595-136">如果梯度下降變得太不穩定，而且收斂過於難以達成，則需要將測量計數向上修改。</span><span class="sxs-lookup"><span data-stu-id="81595-136">One would need to revise the measurement count upward if the gradient descent appears to be too erratic and convergence too hard to achieve.</span></span>

### <a name="training-threads"></a><span data-ttu-id="81595-137">定型執行緒</span><span class="sxs-lookup"><span data-stu-id="81595-137">Training threads</span></span>

<span data-ttu-id="81595-138">這是分類器定型公用程式的機率函數非常少使用，這表示它在參數空間中通常會有許多本機 optima，品質可能會有顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="81595-138">The likelihood function which is the training utility for the classifier is very seldom convex, meaning that it usually has a multitude of local optima in the parameter space that may differ significantly by quality.</span></span> <span data-ttu-id="81595-139">由於 SGD 程式只能收斂到一個特定的最佳方式，因此請務必探索多個起始參數向量。</span><span class="sxs-lookup"><span data-stu-id="81595-139">Since the SGD process can converge to only one specific optimum, it is important to explore multiple starting parameter vectors.</span></span> <span data-ttu-id="81595-140">機器學習服務中的常見做法是隨機初始化這類啟動向量。</span><span class="sxs-lookup"><span data-stu-id="81595-140">Common practice in machine learning is to initialize such starting vectors randomly.</span></span> <span data-ttu-id="81595-141">Q#定型 API 接受這類啟動向量的任意陣列，但基礎程式碼會依序進行探索。</span><span class="sxs-lookup"><span data-stu-id="81595-141">The Q# training API accepts an arbitrary array of such starting vectors but the underlying code explores them sequentially.</span></span> <span data-ttu-id="81595-142">在多核心電腦上，或實際上是在任何平行運算架構上，建議您 Q# 在呼叫之間，使用不同的參數初始化來平行執行數個訓練 API 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="81595-142">On a multicore computer or in fact on any parallel computing architecture it is advisable to perform several calls to Q# training API in parallel with different parameter initializations across the calls.</span></span>

#### <a name="how-to-modify-the-hyperparameters"></a><span data-ttu-id="81595-143">如何修改超參數</span><span class="sxs-lookup"><span data-stu-id="81595-143">How to modify the hyperparameters</span></span>

<span data-ttu-id="81595-144">在 QML 程式庫中，修改超參數的最佳方式是覆寫 UDT 的預設值 [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) 。</span><span class="sxs-lookup"><span data-stu-id="81595-144">In the QML library, the best way to modify the hyperparameters is by overriding the default values of the UDT [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions).</span></span> <span data-ttu-id="81595-145">若要這樣做，我們會使用函式來呼叫它 [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) ，並套用運算子 `w/` 來覆寫預設值。</span><span class="sxs-lookup"><span data-stu-id="81595-145">To do this we call it with the function [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) and apply the operator `w/` to override the default values.</span></span> <span data-ttu-id="81595-146">例如，若要使用100000測量和0.01 的學習率：</span><span class="sxs-lookup"><span data-stu-id="81595-146">For example, to use 100,000 measurements and a learning rate of 0.01:</span></span>
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
