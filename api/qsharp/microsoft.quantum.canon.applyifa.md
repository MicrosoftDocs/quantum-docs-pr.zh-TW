---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699318"
---
# <a name="applyifa-operation"></a><span data-ttu-id="84332-102">ApplyIfA 操作</span><span class="sxs-lookup"><span data-stu-id="84332-102">ApplyIfA operation</span></span>

<span data-ttu-id="84332-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84332-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84332-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84332-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84332-105">套用以傳統位為條件的 adjointable 運算。</span><span class="sxs-lookup"><span data-stu-id="84332-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="84332-106">描述</span><span class="sxs-lookup"><span data-stu-id="84332-106">Description</span></span>

<span data-ttu-id="84332-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="84332-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="84332-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="84332-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="84332-109">尾碼 `A` 表示要套用的作業是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="84332-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="84332-110">輸入</span><span class="sxs-lookup"><span data-stu-id="84332-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="84332-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="84332-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="84332-112">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="84332-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="84332-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="84332-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="84332-114">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="84332-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="84332-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="84332-115">target : 'T</span></span>

<span data-ttu-id="84332-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="84332-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84332-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84332-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84332-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="84332-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84332-119">不要</span><span class="sxs-lookup"><span data-stu-id="84332-119">'T</span></span>

<span data-ttu-id="84332-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="84332-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="84332-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="84332-121">See Also</span></span>

- [<span data-ttu-id="84332-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="84332-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="84332-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="84332-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="84332-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="84332-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)