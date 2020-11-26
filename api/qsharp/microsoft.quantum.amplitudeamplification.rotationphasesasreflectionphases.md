---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191188"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="fa81b-102">RotationPhasesAsReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="fa81b-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="fa81b-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fa81b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fa81b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa81b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa81b-105">將指定為單一量子位旋轉的階段，轉換為指定為部分反射的階段。</span><span class="sxs-lookup"><span data-stu-id="fa81b-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="fa81b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fa81b-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="fa81b-107">rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="fa81b-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="fa81b-108">要轉換成部分反射的單一量子位旋轉陣列。</span><span class="sxs-lookup"><span data-stu-id="fa81b-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="fa81b-109">輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="fa81b-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="fa81b-110">執行指定為部分反射之階段的作業。</span><span class="sxs-lookup"><span data-stu-id="fa81b-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="fa81b-111">參考</span><span class="sxs-lookup"><span data-stu-id="fa81b-111">References</span></span>

<span data-ttu-id="fa81b-112">我們會使用中的慣例</span><span class="sxs-lookup"><span data-stu-id="fa81b-112">We use the convention in</span></span>

- <span data-ttu-id="fa81b-113">[ *G.H. Low，Chuang*](https://arxiv.org/abs/1707.05391) ，以將單一量子位的旋轉階段與反映運算子階段相關聯。</span><span class="sxs-lookup"><span data-stu-id="fa81b-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>