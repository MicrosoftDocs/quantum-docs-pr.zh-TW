---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: 取樣函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700267"
---
# <a name="sampled-function"></a><span data-ttu-id="f82db-102">取樣函數</span><span class="sxs-lookup"><span data-stu-id="f82db-102">Sampled function</span></span>

<span data-ttu-id="f82db-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f82db-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f82db-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f82db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f82db-105">使用指定的排程來取樣指定的陣列。</span><span class="sxs-lookup"><span data-stu-id="f82db-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f82db-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f82db-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="f82db-107">排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="f82db-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="f82db-108">用於取樣值的排程。</span><span class="sxs-lookup"><span data-stu-id="f82db-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="f82db-109">值： t []</span><span class="sxs-lookup"><span data-stu-id="f82db-109">values : 'T[]</span></span>

<span data-ttu-id="f82db-110">要取樣的值陣列。</span><span class="sxs-lookup"><span data-stu-id="f82db-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="f82db-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="f82db-111">Output : 'T[]</span></span>

<span data-ttu-id="f82db-112">值的元素陣列，依照指定的排程。</span><span class="sxs-lookup"><span data-stu-id="f82db-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f82db-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="f82db-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f82db-114">不要</span><span class="sxs-lookup"><span data-stu-id="f82db-114">'T</span></span>

