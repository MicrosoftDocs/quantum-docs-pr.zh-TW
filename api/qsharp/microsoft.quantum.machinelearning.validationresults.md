---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699681"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="776f6-102">ValidationResults 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="776f6-102">ValidationResults user defined type</span></span>

<span data-ttu-id="776f6-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="776f6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="776f6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="776f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="776f6-105">針對一組範例驗證分類器的結果。</span><span class="sxs-lookup"><span data-stu-id="776f6-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="776f6-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="776f6-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="776f6-107">NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="776f6-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="776f6-108">驗證期間觀察到的情形數目。</span><span class="sxs-lookup"><span data-stu-id="776f6-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="776f6-109">NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="776f6-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

