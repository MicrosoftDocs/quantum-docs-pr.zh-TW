---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700194"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="60c8c-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="60c8c-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="60c8c-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="60c8c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="60c8c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60c8c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60c8c-105">由於有資料陣列和其索引的散發，因此會嘗試隨機播放專案。</span><span class="sxs-lookup"><span data-stu-id="60c8c-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="60c8c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="60c8c-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="60c8c-107">data： t []</span><span class="sxs-lookup"><span data-stu-id="60c8c-107">data : 'T[]</span></span>

<span data-ttu-id="60c8c-108">應從中選擇元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="60c8c-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="60c8c-109">indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="60c8c-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="60c8c-110">的索引分佈 `data` 。</span><span class="sxs-lookup"><span data-stu-id="60c8c-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="60c8c-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) </span><span class="sxs-lookup"><span data-stu-id="60c8c-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60c8c-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="60c8c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60c8c-113">不要</span><span class="sxs-lookup"><span data-stu-id="60c8c-113">'T</span></span>

