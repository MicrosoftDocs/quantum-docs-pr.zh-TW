---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843945"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="ff9e5-102">RotationPhasesAsReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="ff9e5-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="ff9e5-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ff9e5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ff9e5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff9e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff9e5-105">將指定為單一量子位旋轉的階段，轉換為指定為部分反射的階段。</span><span class="sxs-lookup"><span data-stu-id="ff9e5-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="ff9e5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ff9e5-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="ff9e5-107">rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="ff9e5-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="ff9e5-108">要轉換成部分反射的單一量子位旋轉陣列。</span><span class="sxs-lookup"><span data-stu-id="ff9e5-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="ff9e5-109">輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ff9e5-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ff9e5-110">執行指定為部分反射之階段的作業。</span><span class="sxs-lookup"><span data-stu-id="ff9e5-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="ff9e5-111">參考資料</span><span class="sxs-lookup"><span data-stu-id="ff9e5-111">References</span></span>

<span data-ttu-id="ff9e5-112">我們會使用中的慣例</span><span class="sxs-lookup"><span data-stu-id="ff9e5-112">We use the convention in</span></span>

- <span data-ttu-id="ff9e5-113">[ *G.H. Low，Chuang*](https://arxiv.org/abs/1707.05391) ，以將單一量子位的旋轉階段與反映運算子階段相關聯。</span><span class="sxs-lookup"><span data-stu-id="ff9e5-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>