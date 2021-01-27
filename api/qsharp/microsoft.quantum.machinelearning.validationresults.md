---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846081"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="949b0-102">ValidationResults 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="949b0-102">ValidationResults user defined type</span></span>

<span data-ttu-id="949b0-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="949b0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="949b0-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="949b0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="949b0-105">針對一組範例驗證分類器的結果。</span><span class="sxs-lookup"><span data-stu-id="949b0-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="949b0-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="949b0-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="949b0-107">NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="949b0-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="949b0-108">驗證期間觀察到的情形數目。</span><span class="sxs-lookup"><span data-stu-id="949b0-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="949b0-109">NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="949b0-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

