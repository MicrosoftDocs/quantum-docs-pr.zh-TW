---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848410"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="a874c-102">InferredLabel 函式</span><span class="sxs-lookup"><span data-stu-id="a874c-102">InferredLabel function</span></span>

<span data-ttu-id="a874c-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a874c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a874c-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a874c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a874c-105">由於分類機率和偏差的考慮，會傳回從該機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="a874c-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="a874c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a874c-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="a874c-107">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a874c-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a874c-108">兩個類別之間的偏差，通常是將分類器定型的結果。</span><span class="sxs-lookup"><span data-stu-id="a874c-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="a874c-109">機率： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a874c-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a874c-110">特定範例的分類機率，通常是因為估計其分類頻率所產生。</span><span class="sxs-lookup"><span data-stu-id="a874c-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="a874c-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a874c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a874c-112">從指定分類機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="a874c-112">The label inferred from the given classification probability.</span></span>