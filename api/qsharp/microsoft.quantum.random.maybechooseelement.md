---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192854"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="82ab6-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="82ab6-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="82ab6-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="82ab6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="82ab6-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="82ab6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="82ab6-105">由於有資料陣列和其索引的散發，因此會嘗試隨機播放專案。</span><span class="sxs-lookup"><span data-stu-id="82ab6-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="82ab6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="82ab6-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="82ab6-107">data： t []</span><span class="sxs-lookup"><span data-stu-id="82ab6-107">data : 'T[]</span></span>

<span data-ttu-id="82ab6-108">應從中選擇元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="82ab6-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="82ab6-109">indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="82ab6-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="82ab6-110">的索引分佈 `data` 。</span><span class="sxs-lookup"><span data-stu-id="82ab6-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="82ab6-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) </span><span class="sxs-lookup"><span data-stu-id="82ab6-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="82ab6-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="82ab6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82ab6-113">不要</span><span class="sxs-lookup"><span data-stu-id="82ab6-113">'T</span></span>

