---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854916"
---
# <a name="schedulelength-function"></a><span data-ttu-id="195d1-102">ScheduleLength 函式</span><span class="sxs-lookup"><span data-stu-id="195d1-102">ScheduleLength function</span></span>

<span data-ttu-id="195d1-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="195d1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="195d1-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="195d1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="195d1-105">傳回指定取樣排程中的元素數目。</span><span class="sxs-lookup"><span data-stu-id="195d1-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="195d1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="195d1-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="195d1-107">排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="195d1-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="195d1-108">要傳回其長度的取樣排程。</span><span class="sxs-lookup"><span data-stu-id="195d1-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="195d1-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="195d1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="195d1-110">給定取樣排程中的元素數目。</span><span class="sxs-lookup"><span data-stu-id="195d1-110">The number of elements in the given sampling schedule.</span></span>