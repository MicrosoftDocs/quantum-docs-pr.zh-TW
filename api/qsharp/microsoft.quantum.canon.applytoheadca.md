---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699172"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="66b24-102">ApplyToHeadCA 操作</span><span class="sxs-lookup"><span data-stu-id="66b24-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="66b24-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="66b24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="66b24-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66b24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66b24-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="66b24-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="66b24-106">描述</span><span class="sxs-lookup"><span data-stu-id="66b24-106">Description</span></span>

<span data-ttu-id="66b24-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="66b24-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="66b24-108">輸入</span><span class="sxs-lookup"><span data-stu-id="66b24-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="66b24-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="66b24-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="66b24-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="66b24-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="66b24-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="66b24-111">targets : 'T[]</span></span>

<span data-ttu-id="66b24-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="66b24-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66b24-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66b24-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66b24-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="66b24-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66b24-115">不要</span><span class="sxs-lookup"><span data-stu-id="66b24-115">'T</span></span>

<span data-ttu-id="66b24-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="66b24-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="66b24-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66b24-117">See Also</span></span>

- [<span data-ttu-id="66b24-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="66b24-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="66b24-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="66b24-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="66b24-120">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="66b24-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)