---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5159eee07f7398cc6194c9907a37b78a63aaf263
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850784"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="e12d7-102">ApplyToElement 操作</span><span class="sxs-lookup"><span data-stu-id="e12d7-102">ApplyToElement operation</span></span>

<span data-ttu-id="e12d7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e12d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e12d7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e12d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e12d7-105">將作業套用至陣列的指定元素。</span><span class="sxs-lookup"><span data-stu-id="e12d7-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e12d7-106">描述</span><span class="sxs-lookup"><span data-stu-id="e12d7-106">Description</span></span>

<span data-ttu-id="e12d7-107">指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="e12d7-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="e12d7-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e12d7-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e12d7-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e12d7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e12d7-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="e12d7-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="e12d7-111">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e12d7-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e12d7-112">目標陣列中的索引。</span><span class="sxs-lookup"><span data-stu-id="e12d7-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e12d7-113">目標： t []</span><span class="sxs-lookup"><span data-stu-id="e12d7-113">targets : 'T[]</span></span>

<span data-ttu-id="e12d7-114">可能目標的陣列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="e12d7-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e12d7-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e12d7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e12d7-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="e12d7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e12d7-117">不要</span><span class="sxs-lookup"><span data-stu-id="e12d7-117">'T</span></span>

<span data-ttu-id="e12d7-118">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="e12d7-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e12d7-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e12d7-119">See Also</span></span>

- [<span data-ttu-id="e12d7-120">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="e12d7-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="e12d7-121">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="e12d7-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="e12d7-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="e12d7-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)