---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: 取樣函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854938"
---
# <a name="sampled-function"></a><span data-ttu-id="e4fb2-102">取樣函數</span><span class="sxs-lookup"><span data-stu-id="e4fb2-102">Sampled function</span></span>

<span data-ttu-id="e4fb2-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e4fb2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e4fb2-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e4fb2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e4fb2-105">使用指定的排程來取樣指定的陣列。</span><span class="sxs-lookup"><span data-stu-id="e4fb2-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e4fb2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e4fb2-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="e4fb2-107">排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e4fb2-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="e4fb2-108">用於取樣值的排程。</span><span class="sxs-lookup"><span data-stu-id="e4fb2-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="e4fb2-109">值： t []</span><span class="sxs-lookup"><span data-stu-id="e4fb2-109">values : 'T[]</span></span>

<span data-ttu-id="e4fb2-110">要取樣的值陣列。</span><span class="sxs-lookup"><span data-stu-id="e4fb2-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="e4fb2-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="e4fb2-111">Output : 'T[]</span></span>

<span data-ttu-id="e4fb2-112">值的元素陣列，依照指定的排程。</span><span class="sxs-lookup"><span data-stu-id="e4fb2-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e4fb2-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="e4fb2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4fb2-114">不要</span><span class="sxs-lookup"><span data-stu-id="e4fb2-114">'T</span></span>

