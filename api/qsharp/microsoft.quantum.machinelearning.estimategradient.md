---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699605"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="dd6a5-102">EstimateGradient 操作</span><span class="sxs-lookup"><span data-stu-id="dd6a5-102">EstimateGradient operation</span></span>

<span data-ttu-id="dd6a5-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dd6a5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dd6a5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd6a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd6a5-105">針對特定模型和指定編碼的輸入，預估順序分類器的定型漸層。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="dd6a5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dd6a5-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="dd6a5-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="dd6a5-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="dd6a5-108">要估計其漸層的連續模型。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="dd6a5-109">encodedInput： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="dd6a5-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="dd6a5-110">順序分類器的輸入，編碼為狀態準備作業。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="dd6a5-111">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd6a5-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd6a5-112">用來估計漸層的度量數目。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="dd6a5-113">輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd6a5-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd6a5-114">給定輸入和模型參數上定型漸層的估計值。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd6a5-115">備註</span><span class="sxs-lookup"><span data-stu-id="dd6a5-115">Remarks</span></span>

<span data-ttu-id="dd6a5-116">這項作業會使用 Hadamard 測試和參數移位技術來預估漸層。</span><span class="sxs-lookup"><span data-stu-id="dd6a5-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>