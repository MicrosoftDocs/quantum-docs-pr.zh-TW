---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700262"
---
# <a name="schedulelength-function"></a><span data-ttu-id="f9906-102">ScheduleLength 函式</span><span class="sxs-lookup"><span data-stu-id="f9906-102">ScheduleLength function</span></span>

<span data-ttu-id="f9906-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9906-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f9906-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9906-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9906-105">傳回指定取樣排程中的元素數目。</span><span class="sxs-lookup"><span data-stu-id="f9906-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="f9906-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f9906-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="f9906-107">排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="f9906-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="f9906-108">要傳回其長度的取樣排程。</span><span class="sxs-lookup"><span data-stu-id="f9906-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="f9906-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9906-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9906-110">給定取樣排程中的元素數目。</span><span class="sxs-lookup"><span data-stu-id="f9906-110">The number of elements in the given sampling schedule.</span></span>