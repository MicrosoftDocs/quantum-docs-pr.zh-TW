---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218762"
---
# <a name="applyifa-operation"></a><span data-ttu-id="42634-102">ApplyIfA 操作</span><span class="sxs-lookup"><span data-stu-id="42634-102">ApplyIfA operation</span></span>

<span data-ttu-id="42634-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42634-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42634-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42634-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42634-105">套用以傳統位為條件的 adjointable 運算。</span><span class="sxs-lookup"><span data-stu-id="42634-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="42634-106">描述</span><span class="sxs-lookup"><span data-stu-id="42634-106">Description</span></span>

<span data-ttu-id="42634-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="42634-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="42634-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="42634-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="42634-109">尾碼 `A` 表示要套用的作業是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="42634-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="42634-110">輸入</span><span class="sxs-lookup"><span data-stu-id="42634-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="42634-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="42634-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="42634-112">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="42634-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="42634-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42634-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42634-114">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="42634-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="42634-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="42634-115">target : 'T</span></span>

<span data-ttu-id="42634-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="42634-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42634-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42634-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42634-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="42634-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42634-119">不要</span><span class="sxs-lookup"><span data-stu-id="42634-119">'T</span></span>

<span data-ttu-id="42634-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="42634-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="42634-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42634-121">See Also</span></span>

- [<span data-ttu-id="42634-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="42634-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="42634-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="42634-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="42634-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="42634-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)