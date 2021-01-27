---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856841"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="9bcd4-102">PurifiedMixedStateRequirements 函式</span><span class="sxs-lookup"><span data-stu-id="9bcd4-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="9bcd4-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9bcd4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9bcd4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bcd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bcd4-105">傳回必須配置才能套用所傳回之作業的量子位總數 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="9bcd4-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="9bcd4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9bcd4-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="9bcd4-107">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bcd4-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9bcd4-108">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="9bcd4-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="9bcd4-109">nCoefficients： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9bcd4-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9bcd4-110">要在準備混合狀態時指定的係數數目。</span><span class="sxs-lookup"><span data-stu-id="9bcd4-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="9bcd4-111">輸出： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="9bcd4-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="9bcd4-112">描述每個所需的量子位數目，以及函式所使用的每個索引和垃圾暫存器 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="9bcd4-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bcd4-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9bcd4-113">See Also</span></span>

- [<span data-ttu-id="9bcd4-114">PurifiedMixedState。</span><span class="sxs-lookup"><span data-stu-id="9bcd4-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)