---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850603"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="24402-102">ApplyToHeadCA 操作</span><span class="sxs-lookup"><span data-stu-id="24402-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="24402-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24402-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24402-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24402-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24402-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="24402-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="24402-106">描述</span><span class="sxs-lookup"><span data-stu-id="24402-106">Description</span></span>

<span data-ttu-id="24402-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="24402-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="24402-108">輸入</span><span class="sxs-lookup"><span data-stu-id="24402-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="24402-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="24402-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="24402-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="24402-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="24402-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="24402-111">targets : 'T[]</span></span>

<span data-ttu-id="24402-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="24402-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24402-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24402-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="24402-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="24402-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24402-115">不要</span><span class="sxs-lookup"><span data-stu-id="24402-115">'T</span></span>

<span data-ttu-id="24402-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="24402-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="24402-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="24402-117">See Also</span></span>

- [<span data-ttu-id="24402-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="24402-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="24402-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="24402-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="24402-120">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="24402-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)