---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191358"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="988de-102">RotationPhases 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="988de-102">RotationPhases user defined type</span></span>

<span data-ttu-id="988de-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="988de-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="988de-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="988de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="988de-105">以振幅放大的一連串單一量子位旋轉的階段。</span><span class="sxs-lookup"><span data-stu-id="988de-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="988de-106">備註</span><span class="sxs-lookup"><span data-stu-id="988de-106">Remarks</span></span>

<span data-ttu-id="988de-107">第一個參數是反映的階段陣列，以單一量子位旋轉的乘積表示。</span><span class="sxs-lookup"><span data-stu-id="988de-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="988de-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="988de-108">[ G.H.</span></span> <span data-ttu-id="988de-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="988de-109">Low, I. L.</span></span> <span data-ttu-id="988de-110">Chuang， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="988de-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>