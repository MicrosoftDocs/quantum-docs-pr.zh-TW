---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699174"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="55d05-102">ApplyToHeadC 操作</span><span class="sxs-lookup"><span data-stu-id="55d05-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="55d05-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55d05-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55d05-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55d05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55d05-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="55d05-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="55d05-106">描述</span><span class="sxs-lookup"><span data-stu-id="55d05-106">Description</span></span>

<span data-ttu-id="55d05-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="55d05-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="55d05-108">輸入</span><span class="sxs-lookup"><span data-stu-id="55d05-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="55d05-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="55d05-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="55d05-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="55d05-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="55d05-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="55d05-111">targets : 'T[]</span></span>

<span data-ttu-id="55d05-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="55d05-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55d05-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55d05-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55d05-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="55d05-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55d05-115">不要</span><span class="sxs-lookup"><span data-stu-id="55d05-115">'T</span></span>

<span data-ttu-id="55d05-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="55d05-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="55d05-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55d05-117">See Also</span></span>

- [<span data-ttu-id="55d05-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="55d05-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="55d05-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="55d05-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="55d05-120">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="55d05-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)