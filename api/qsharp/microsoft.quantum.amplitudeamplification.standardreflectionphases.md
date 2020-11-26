---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191120"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="0362a-102">StandardReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="0362a-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="0362a-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0362a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0362a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0362a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0362a-105">計算標準振幅放大的部分反映階段。</span><span class="sxs-lookup"><span data-stu-id="0362a-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="0362a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0362a-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="0362a-107">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0362a-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0362a-108">要為其產生部分反映階段的波幅放大反覆運算數目。</span><span class="sxs-lookup"><span data-stu-id="0362a-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="0362a-109">輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="0362a-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="0362a-110">執行指定為部分反射之階段的作業</span><span class="sxs-lookup"><span data-stu-id="0362a-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="0362a-111">備註</span><span class="sxs-lookup"><span data-stu-id="0362a-111">Remarks</span></span>

<span data-ttu-id="0362a-112">所有階段都是 $ \pi $，但第一次反映有關「啟動狀態」和「上次反映」的目標狀態，也就是 $0 $。</span><span class="sxs-lookup"><span data-stu-id="0362a-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>