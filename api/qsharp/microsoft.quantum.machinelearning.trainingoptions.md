---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842772"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="b617a-102">TrainingOptions 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="b617a-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="b617a-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b617a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b617a-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b617a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b617a-105">要用於定型量子分類器的選項組合。</span><span class="sxs-lookup"><span data-stu-id="b617a-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="b617a-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="b617a-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="b617a-107">LearningRate： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b617a-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b617a-108">在定型步驟期間更新模型參數時，應重新調整漸層的學習速率。</span><span class="sxs-lookup"><span data-stu-id="b617a-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="b617a-109">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b617a-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b617a-110">以量子狀態準備範例時所要使用的近似值容錯。</span><span class="sxs-lookup"><span data-stu-id="b617a-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="b617a-111">MinibatchSize： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b617a-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b617a-112">要在每個定型迷你批次中使用的樣本數目。</span><span class="sxs-lookup"><span data-stu-id="b617a-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="b617a-113">NMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b617a-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b617a-114">測量每個分類結果以預估分類機率的次數。</span><span class="sxs-lookup"><span data-stu-id="b617a-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="b617a-115">MaxEpochs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b617a-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b617a-116">要為每個模型定型的 epoch 數目上限。</span><span class="sxs-lookup"><span data-stu-id="b617a-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="b617a-117">MaxStalls： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b617a-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b617a-118">在失敗之前，允許訓練 epoch 停止 (大約零梯度) 的最大次數。</span><span class="sxs-lookup"><span data-stu-id="b617a-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="b617a-119">StochasticRescaleFactor： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b617a-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b617a-120">重試更新之前，要調整停止的模型的數量。</span><span class="sxs-lookup"><span data-stu-id="b617a-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="b617a-121">ScoringPeriod： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b617a-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b617a-122">計分點之間要執行的漸層步驟數目。</span><span class="sxs-lookup"><span data-stu-id="b617a-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="b617a-123">為了達到最佳精確度，請設定為1。</span><span class="sxs-lookup"><span data-stu-id="b617a-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="b617a-124">VerboseMessage： [字串](xref:microsoft.quantum.lang-ref.string) -> [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b617a-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="b617a-125">可以用來提供詳細資訊意見反應的函數。</span><span class="sxs-lookup"><span data-stu-id="b617a-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="b617a-126">備註</span><span class="sxs-lookup"><span data-stu-id="b617a-126">Remarks</span></span>

<span data-ttu-id="b617a-127">此 UDT 不應該直接建立，而是藉由呼叫 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 然後使用 `w/` 運算子來覆寫不同的預設值來指定。</span><span class="sxs-lookup"><span data-stu-id="b617a-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="b617a-128">例如，若要使用100000度量和最多8個定型 epoch：</span><span class="sxs-lookup"><span data-stu-id="b617a-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="b617a-129">參考資料</span><span class="sxs-lookup"><span data-stu-id="b617a-129">References</span></span>

- [<span data-ttu-id="b617a-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="b617a-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)