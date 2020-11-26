---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207967"
---
# <a name="applytotail-operation"></a><span data-ttu-id="b5652-102">ApplyToTail 操作</span><span class="sxs-lookup"><span data-stu-id="b5652-102">ApplyToTail operation</span></span>

<span data-ttu-id="b5652-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5652-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5652-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5652-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5652-105">將作業套用至陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="b5652-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b5652-106">描述</span><span class="sxs-lookup"><span data-stu-id="b5652-106">Description</span></span>

<span data-ttu-id="b5652-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="b5652-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b5652-108">輸入</span><span class="sxs-lookup"><span data-stu-id="b5652-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="b5652-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5652-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b5652-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="b5652-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b5652-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="b5652-111">targets : 'T[]</span></span>

<span data-ttu-id="b5652-112">目標的陣列，最後會將其套用至其中 `op` 。</span><span class="sxs-lookup"><span data-stu-id="b5652-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5652-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5652-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5652-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="b5652-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5652-115">不要</span><span class="sxs-lookup"><span data-stu-id="b5652-115">'T</span></span>

<span data-ttu-id="b5652-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="b5652-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5652-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5652-117">See Also</span></span>

- [<span data-ttu-id="b5652-118">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="b5652-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="b5652-119">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="b5652-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="b5652-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b5652-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)