---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 情形函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211673"
---
# <a name="misclassifications-function"></a><span data-ttu-id="a9840-102">情形函式</span><span class="sxs-lookup"><span data-stu-id="a9840-102">Misclassifications function</span></span>

<span data-ttu-id="a9840-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a9840-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a9840-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a9840-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a9840-105">假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引。</span><span class="sxs-lookup"><span data-stu-id="a9840-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a9840-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a9840-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="a9840-107">inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a9840-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a9840-108">針對指定定型或驗證集所推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="a9840-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="a9840-109">actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a9840-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a9840-110">給定定型或驗證集的真實標籤。</span><span class="sxs-lookup"><span data-stu-id="a9840-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="a9840-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a9840-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a9840-112">索引的陣列 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="a9840-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>