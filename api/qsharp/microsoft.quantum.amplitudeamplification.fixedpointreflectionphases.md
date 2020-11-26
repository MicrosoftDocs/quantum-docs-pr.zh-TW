---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191443"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="6d6cd-102">FixedPointReflectionPhases 函式</span><span class="sxs-lookup"><span data-stu-id="6d6cd-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="6d6cd-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6d6cd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6d6cd-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d6cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d6cd-105">計算固定點振幅放大的部分反映階段。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="6d6cd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6d6cd-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="6d6cd-107">nQueries： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d6cd-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d6cd-108">Oracle 狀態準備的查詢數目。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="6d6cd-109">必須是奇數整數。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="6d6cd-110">successMin： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6d6cd-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6d6cd-111">目標最小成功機率。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="6d6cd-112">輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="6d6cd-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="6d6cd-113">可用於固定點振幅放大量子演算法實的階段陣列。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="6d6cd-114">參考</span><span class="sxs-lookup"><span data-stu-id="6d6cd-114">References</span></span>

<span data-ttu-id="6d6cd-115">我們會使用「具有最佳查詢數目的固定點波幅放大」中的階段</span><span class="sxs-lookup"><span data-stu-id="6d6cd-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="6d6cd-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 另請參閱「複合量子閘道的方法」</span><span class="sxs-lookup"><span data-stu-id="6d6cd-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="6d6cd-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) 格式的階段 `RotationPhases` 。</span><span class="sxs-lookup"><span data-stu-id="6d6cd-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>