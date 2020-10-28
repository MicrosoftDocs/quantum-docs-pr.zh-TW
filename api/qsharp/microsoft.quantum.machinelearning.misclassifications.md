---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 情形函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700598"
---
# <a name="misclassifications-function"></a><span data-ttu-id="0283f-102">情形函式</span><span class="sxs-lookup"><span data-stu-id="0283f-102">Misclassifications function</span></span>

<span data-ttu-id="0283f-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0283f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0283f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0283f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0283f-105">假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引。</span><span class="sxs-lookup"><span data-stu-id="0283f-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0283f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0283f-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="0283f-107">inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0283f-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0283f-108">針對指定定型或驗證集所推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="0283f-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="0283f-109">actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0283f-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0283f-110">給定定型或驗證集的真實標籤。</span><span class="sxs-lookup"><span data-stu-id="0283f-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="0283f-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0283f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0283f-112">索引的陣列 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="0283f-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>