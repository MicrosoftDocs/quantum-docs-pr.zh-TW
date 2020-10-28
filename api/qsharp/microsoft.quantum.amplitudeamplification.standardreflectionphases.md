---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700070"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="a330f-102">StandardReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="a330f-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="a330f-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a330f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a330f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a330f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a330f-105">計算標準振幅放大的部分反映階段。</span><span class="sxs-lookup"><span data-stu-id="a330f-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="a330f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a330f-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="a330f-107">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a330f-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a330f-108">要為其產生部分反映階段的波幅放大反覆運算數目。</span><span class="sxs-lookup"><span data-stu-id="a330f-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="a330f-109">輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a330f-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a330f-110">執行指定為部分反射之階段的作業</span><span class="sxs-lookup"><span data-stu-id="a330f-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="a330f-111">備註</span><span class="sxs-lookup"><span data-stu-id="a330f-111">Remarks</span></span>

<span data-ttu-id="a330f-112">所有階段都是 $ \pi $，但第一次反映有關「啟動狀態」和「上次反映」的目標狀態，也就是 $0 $。</span><span class="sxs-lookup"><span data-stu-id="a330f-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>