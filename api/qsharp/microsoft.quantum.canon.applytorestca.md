---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699148"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="a24a9-102">ApplyToRestCA 操作</span><span class="sxs-lookup"><span data-stu-id="a24a9-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="a24a9-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a24a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a24a9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a24a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a24a9-105">將作業套用至陣列的第一個元素以外的所有專案。</span><span class="sxs-lookup"><span data-stu-id="a24a9-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a24a9-106">描述</span><span class="sxs-lookup"><span data-stu-id="a24a9-106">Description</span></span>

<span data-ttu-id="a24a9-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="a24a9-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a24a9-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a24a9-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="a24a9-109">op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a24a9-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a24a9-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="a24a9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a24a9-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="a24a9-111">targets : 'T[]</span></span>

<span data-ttu-id="a24a9-112">目標的陣列，其中全部都將套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="a24a9-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a24a9-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a24a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a24a9-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="a24a9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a24a9-115">不要</span><span class="sxs-lookup"><span data-stu-id="a24a9-115">'T</span></span>

<span data-ttu-id="a24a9-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="a24a9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a24a9-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a24a9-117">See Also</span></span>

- [<span data-ttu-id="a24a9-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="a24a9-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="a24a9-119">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="a24a9-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="a24a9-120">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="a24a9-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)