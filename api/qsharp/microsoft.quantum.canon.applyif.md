---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699317"
---
# <a name="applyif-operation"></a><span data-ttu-id="25ac9-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="25ac9-102">ApplyIf operation</span></span>

<span data-ttu-id="25ac9-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25ac9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25ac9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25ac9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25ac9-105">在傳統位上套用條件運算。</span><span class="sxs-lookup"><span data-stu-id="25ac9-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="25ac9-106">描述</span><span class="sxs-lookup"><span data-stu-id="25ac9-106">Description</span></span>

<span data-ttu-id="25ac9-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="25ac9-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="25ac9-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="25ac9-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="25ac9-109">輸入</span><span class="sxs-lookup"><span data-stu-id="25ac9-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="25ac9-110">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25ac9-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="25ac9-111">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="25ac9-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="25ac9-112">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="25ac9-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="25ac9-113">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="25ac9-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="25ac9-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="25ac9-114">target : 'T</span></span>

<span data-ttu-id="25ac9-115">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="25ac9-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25ac9-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25ac9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25ac9-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="25ac9-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25ac9-118">不要</span><span class="sxs-lookup"><span data-stu-id="25ac9-118">'T</span></span>

<span data-ttu-id="25ac9-119">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="25ac9-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="25ac9-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="25ac9-120">See Also</span></span>

- [<span data-ttu-id="25ac9-121">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="25ac9-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="25ac9-122">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="25ac9-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="25ac9-123">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="25ac9-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)