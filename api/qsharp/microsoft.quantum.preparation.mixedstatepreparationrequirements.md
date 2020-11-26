---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228690"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a><span data-ttu-id="855f6-102">MixedStatePreparationRequirements 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="855f6-102">MixedStatePreparationRequirements user defined type</span></span>

<span data-ttu-id="855f6-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="855f6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="855f6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="855f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="855f6-105">代表準備指定的混合狀態所需的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="855f6-105">Represents the number of qubits required in order to prepare a given mixed state.</span></span>

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a><span data-ttu-id="855f6-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="855f6-106">Named Items</span></span>

### <a name="ntotalqubits--int"></a><span data-ttu-id="855f6-107">NTotalQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="855f6-107">NTotalQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="nindexqubits--int"></a><span data-ttu-id="855f6-108">NIndexQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="855f6-108">NIndexQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="ngarbagequbits--int"></a><span data-ttu-id="855f6-109">NGarbageQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="855f6-109">NGarbageQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="see-also"></a><span data-ttu-id="855f6-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="855f6-110">See Also</span></span>

- [<span data-ttu-id="855f6-111">PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="855f6-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)