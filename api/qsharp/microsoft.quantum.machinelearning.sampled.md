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
# <a name="sampled-function"></a>取樣函數

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


使用指定的排程來取樣指定的陣列。

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="schedule--samplingschedule"></a>排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

用於取樣值的排程。


### <a name="values--t"></a>值： t []

要取樣的值陣列。



## <a name="output--t"></a>Output： t []

值的元素陣列，依照指定的排程。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

