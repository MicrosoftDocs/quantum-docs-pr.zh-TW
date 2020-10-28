---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700079"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="a2290-102">RotationPhases 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="a2290-102">RotationPhases user defined type</span></span>

<span data-ttu-id="a2290-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a2290-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a2290-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2290-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2290-105">以振幅放大的一連串單一量子位旋轉的階段。</span><span class="sxs-lookup"><span data-stu-id="a2290-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="a2290-106">備註</span><span class="sxs-lookup"><span data-stu-id="a2290-106">Remarks</span></span>

<span data-ttu-id="a2290-107">第一個參數是反映的階段陣列，以單一量子位旋轉的乘積表示。</span><span class="sxs-lookup"><span data-stu-id="a2290-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="a2290-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="a2290-108">[ G.H.</span></span> <span data-ttu-id="a2290-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="a2290-109">Low, I. L.</span></span> <span data-ttu-id="a2290-110">Chuang， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="a2290-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>