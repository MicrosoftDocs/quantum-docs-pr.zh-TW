---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207848"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="6ac16-102">ApplyToTailCA 操作</span><span class="sxs-lookup"><span data-stu-id="6ac16-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="6ac16-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ac16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ac16-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ac16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ac16-105">將作業套用至陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="6ac16-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6ac16-106">描述</span><span class="sxs-lookup"><span data-stu-id="6ac16-106">Description</span></span>

<span data-ttu-id="6ac16-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="6ac16-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6ac16-108">輸入</span><span class="sxs-lookup"><span data-stu-id="6ac16-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="6ac16-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6ac16-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6ac16-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="6ac16-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6ac16-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="6ac16-111">targets : 'T[]</span></span>

<span data-ttu-id="6ac16-112">目標的陣列，最後會將其套用至其中 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6ac16-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ac16-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ac16-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ac16-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="6ac16-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ac16-115">不要</span><span class="sxs-lookup"><span data-stu-id="6ac16-115">'T</span></span>

<span data-ttu-id="6ac16-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="6ac16-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac16-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ac16-117">See Also</span></span>

- [<span data-ttu-id="6ac16-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="6ac16-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="6ac16-119">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="6ac16-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="6ac16-120">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="6ac16-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)