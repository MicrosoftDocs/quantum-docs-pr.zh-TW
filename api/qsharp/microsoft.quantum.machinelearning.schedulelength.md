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
# <a name="schedulelength-function"></a>ScheduleLength 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


傳回指定取樣排程中的元素數目。

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a>輸入

### <a name="schedule--samplingschedule"></a>排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

要傳回其長度的取樣排程。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

給定取樣排程中的元素數目。