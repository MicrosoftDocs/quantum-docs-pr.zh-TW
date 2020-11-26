---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208851"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="42955-102">ApplyToElementCA 操作</span><span class="sxs-lookup"><span data-stu-id="42955-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="42955-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42955-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42955-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42955-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42955-105">將作業套用至陣列的指定元素。</span><span class="sxs-lookup"><span data-stu-id="42955-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="42955-106">描述</span><span class="sxs-lookup"><span data-stu-id="42955-106">Description</span></span>

<span data-ttu-id="42955-107">指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="42955-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="42955-108">輸入</span><span class="sxs-lookup"><span data-stu-id="42955-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="42955-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="42955-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="42955-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="42955-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="42955-111">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="42955-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="42955-112">目標陣列中的索引。</span><span class="sxs-lookup"><span data-stu-id="42955-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="42955-113">目標： t []</span><span class="sxs-lookup"><span data-stu-id="42955-113">targets : 'T[]</span></span>

<span data-ttu-id="42955-114">可能目標的陣列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="42955-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42955-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42955-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42955-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="42955-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42955-117">不要</span><span class="sxs-lookup"><span data-stu-id="42955-117">'T</span></span>

<span data-ttu-id="42955-118">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="42955-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="42955-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42955-119">See Also</span></span>

- [<span data-ttu-id="42955-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="42955-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="42955-121">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="42955-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="42955-122">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="42955-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)