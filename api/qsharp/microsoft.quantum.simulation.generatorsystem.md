---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858417"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="58994-102">GeneratorSystem 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="58994-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="58994-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="58994-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="58994-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58994-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58994-105">代表 es 的集合 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="58994-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="58994-106">我們會使用單一索引整數逐一查看此集合，並假設為已知的集合大小。</span><span class="sxs-lookup"><span data-stu-id="58994-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="58994-107">備註</span><span class="sxs-lookup"><span data-stu-id="58994-107">Remarks</span></span>

<span data-ttu-id="58994-108">您 `GeneratorSystem` 可以使用函數輕鬆地定義的實例 <xref:microsoft.quantum.arrays.lookupfunction> 。</span><span class="sxs-lookup"><span data-stu-id="58994-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="58994-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58994-109">See Also</span></span>

- [<span data-ttu-id="58994-110">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="58994-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)