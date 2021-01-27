---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841327"
---
# <a name="applytohead-operation"></a><span data-ttu-id="e270b-102">ApplyToHead 操作</span><span class="sxs-lookup"><span data-stu-id="e270b-102">ApplyToHead operation</span></span>

<span data-ttu-id="e270b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e270b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e270b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e270b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e270b-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="e270b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e270b-106">描述</span><span class="sxs-lookup"><span data-stu-id="e270b-106">Description</span></span>

<span data-ttu-id="e270b-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="e270b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e270b-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e270b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e270b-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e270b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e270b-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="e270b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e270b-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="e270b-111">targets : 'T[]</span></span>

<span data-ttu-id="e270b-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="e270b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e270b-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e270b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e270b-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="e270b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e270b-115">不要</span><span class="sxs-lookup"><span data-stu-id="e270b-115">'T</span></span>

<span data-ttu-id="e270b-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="e270b-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="e270b-117">範例</span><span class="sxs-lookup"><span data-stu-id="e270b-117">Example</span></span>

<span data-ttu-id="e270b-118">下列 Q # 程式碼片段是相等的：</span><span class="sxs-lookup"><span data-stu-id="e270b-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="e270b-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e270b-119">See Also</span></span>

- [<span data-ttu-id="e270b-120">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="e270b-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="e270b-121">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e270b-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e270b-122">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="e270b-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)