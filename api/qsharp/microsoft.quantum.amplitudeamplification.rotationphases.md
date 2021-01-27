---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843974"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="bd411-102">RotationPhases 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="bd411-102">RotationPhases user defined type</span></span>

<span data-ttu-id="bd411-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bd411-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bd411-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd411-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd411-105">以振幅放大的一連串單一量子位旋轉的階段。</span><span class="sxs-lookup"><span data-stu-id="bd411-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="bd411-106">備註</span><span class="sxs-lookup"><span data-stu-id="bd411-106">Remarks</span></span>

<span data-ttu-id="bd411-107">第一個參數是反映的階段陣列，以單一量子位旋轉的乘積表示。</span><span class="sxs-lookup"><span data-stu-id="bd411-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="bd411-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="bd411-108">[ G.H.</span></span> <span data-ttu-id="bd411-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="bd411-109">Low, I. L.</span></span> <span data-ttu-id="bd411-110">Chuang， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="bd411-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>