---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697683"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="5958e-102">LabeledSample 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="5958e-102">LabeledSample user defined type</span></span>

<span data-ttu-id="5958e-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5958e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5958e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5958e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5958e-105">範例，其標記為該範例所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="5958e-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="5958e-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="5958e-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="5958e-107">功能： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5958e-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5958e-108">給定範例的特徵向量。</span><span class="sxs-lookup"><span data-stu-id="5958e-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="5958e-109">標籤： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5958e-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5958e-110">此範例所屬類別的整數標籤。</span><span class="sxs-lookup"><span data-stu-id="5958e-110">An integer label for the class to which this sample belongs.</span></span>