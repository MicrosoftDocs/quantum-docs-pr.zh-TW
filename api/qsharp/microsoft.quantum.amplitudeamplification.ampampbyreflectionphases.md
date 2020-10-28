---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByReflectionPhases
title: AmpAmpByReflectionPhases 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".
ms.openlocfilehash: 430979b4527e37e878c57294b41d0637929c758d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699621"
---
# <a name="ampampbyreflectionphases-function"></a><span data-ttu-id="607fa-102">AmpAmpByReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="607fa-102">AmpAmpByReflectionPhases function</span></span>

<span data-ttu-id="607fa-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="607fa-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="607fa-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="607fa-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="607fa-105">AmpAmpByReflectionPhases 已被取代。</span><span class="sxs-lookup"><span data-stu-id="607fa-105">AmpAmpByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="607fa-106">請改用 <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections>。</span><span class="sxs-lookup"><span data-stu-id="607fa-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="607fa-107">請使用 @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections"。</span><span class="sxs-lookup"><span data-stu-id="607fa-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="607fa-108">輸入</span><span class="sxs-lookup"><span data-stu-id="607fa-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="607fa-109">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="607fa-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="607fa-110">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="607fa-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="607fa-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="607fa-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="607fa-112">Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="607fa-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

