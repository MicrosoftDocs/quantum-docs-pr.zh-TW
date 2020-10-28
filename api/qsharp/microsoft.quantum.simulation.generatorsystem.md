---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700878"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="f3979-102">GeneratorSystem 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="f3979-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="f3979-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f3979-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f3979-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3979-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3979-105">代表 es 的集合 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="f3979-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="f3979-106">我們會使用單一索引整數逐一查看此集合，並假設為已知的集合大小。</span><span class="sxs-lookup"><span data-stu-id="f3979-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="f3979-107">備註</span><span class="sxs-lookup"><span data-stu-id="f3979-107">Remarks</span></span>

<span data-ttu-id="f3979-108">您 `GeneratorSystem` 可以使用函數輕鬆地定義的實例 <xref:microsoft.quantum.arrays.lookupfunction> 。</span><span class="sxs-lookup"><span data-stu-id="f3979-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3979-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3979-109">See Also</span></span>

- [<span data-ttu-id="f3979-110">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="f3979-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)