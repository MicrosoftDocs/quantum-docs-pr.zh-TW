---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699316"
---
# <a name="applyifc-operation"></a><span data-ttu-id="01410-102">ApplyIfC 操作</span><span class="sxs-lookup"><span data-stu-id="01410-102">ApplyIfC operation</span></span>

<span data-ttu-id="01410-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01410-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01410-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01410-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01410-105">針對傳統位套用可控的作業。</span><span class="sxs-lookup"><span data-stu-id="01410-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="01410-106">描述</span><span class="sxs-lookup"><span data-stu-id="01410-106">Description</span></span>

<span data-ttu-id="01410-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="01410-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="01410-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="01410-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="01410-109">尾碼 `C` 表示要套用的作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="01410-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="01410-110">輸入</span><span class="sxs-lookup"><span data-stu-id="01410-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="01410-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="01410-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="01410-112">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="01410-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="01410-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="01410-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01410-114">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="01410-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="01410-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="01410-115">target : 'T</span></span>

<span data-ttu-id="01410-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="01410-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01410-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01410-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="01410-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="01410-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01410-119">不要</span><span class="sxs-lookup"><span data-stu-id="01410-119">'T</span></span>

<span data-ttu-id="01410-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="01410-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="01410-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="01410-121">See Also</span></span>

- [<span data-ttu-id="01410-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="01410-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="01410-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="01410-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="01410-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="01410-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)