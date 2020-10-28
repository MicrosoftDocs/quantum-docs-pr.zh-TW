---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697227"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="50291-102">NMisclassifications 函式</span><span class="sxs-lookup"><span data-stu-id="50291-102">NMisclassifications function</span></span>

<span data-ttu-id="50291-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="50291-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="50291-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50291-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50291-105">假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引數目。</span><span class="sxs-lookup"><span data-stu-id="50291-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="50291-106">輸入</span><span class="sxs-lookup"><span data-stu-id="50291-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="50291-107">提議： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="50291-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="50291-108">實際： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="50291-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="50291-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50291-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50291-110">索引的數目 `idx` `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="50291-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>