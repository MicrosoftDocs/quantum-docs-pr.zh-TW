---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211588"
---
# <a name="schedulelength-function"></a>ScheduleLength 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回指定取樣排程中的元素數目。

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a>輸入

### <a name="schedule--samplingschedule"></a>排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

要傳回其長度的取樣排程。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

給定取樣排程中的元素數目。