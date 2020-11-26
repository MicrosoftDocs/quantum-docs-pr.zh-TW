---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208868"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="dfa61-102">ApplyToElementA 操作</span><span class="sxs-lookup"><span data-stu-id="dfa61-102">ApplyToElementA operation</span></span>

<span data-ttu-id="dfa61-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dfa61-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dfa61-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfa61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfa61-105">將作業套用至陣列的指定元素。</span><span class="sxs-lookup"><span data-stu-id="dfa61-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="dfa61-106">描述</span><span class="sxs-lookup"><span data-stu-id="dfa61-106">Description</span></span>

<span data-ttu-id="dfa61-107">指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="dfa61-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="dfa61-108">輸入</span><span class="sxs-lookup"><span data-stu-id="dfa61-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="dfa61-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="dfa61-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dfa61-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="dfa61-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="dfa61-111">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfa61-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfa61-112">目標陣列中的索引。</span><span class="sxs-lookup"><span data-stu-id="dfa61-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="dfa61-113">目標： t []</span><span class="sxs-lookup"><span data-stu-id="dfa61-113">targets : 'T[]</span></span>

<span data-ttu-id="dfa61-114">可能目標的陣列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="dfa61-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfa61-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfa61-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dfa61-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="dfa61-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dfa61-117">不要</span><span class="sxs-lookup"><span data-stu-id="dfa61-117">'T</span></span>

<span data-ttu-id="dfa61-118">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="dfa61-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa61-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dfa61-119">See Also</span></span>

- [<span data-ttu-id="dfa61-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="dfa61-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="dfa61-121">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="dfa61-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="dfa61-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="dfa61-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)