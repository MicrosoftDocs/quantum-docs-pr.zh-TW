---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846970"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="53cc2-102">LabeledSample 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="53cc2-102">LabeledSample user defined type</span></span>

<span data-ttu-id="53cc2-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="53cc2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="53cc2-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="53cc2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="53cc2-105">範例，其標記為該範例所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="53cc2-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="53cc2-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="53cc2-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="53cc2-107">功能： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="53cc2-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="53cc2-108">給定範例的特徵向量。</span><span class="sxs-lookup"><span data-stu-id="53cc2-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="53cc2-109">標籤： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53cc2-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53cc2-110">此範例所屬類別的整數標籤。</span><span class="sxs-lookup"><span data-stu-id="53cc2-110">An integer label for the class to which this sample belongs.</span></span>