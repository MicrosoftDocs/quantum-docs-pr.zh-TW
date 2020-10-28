---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699175"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="c08da-102">ApplyToHeadA 操作</span><span class="sxs-lookup"><span data-stu-id="c08da-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="c08da-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c08da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c08da-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c08da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c08da-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="c08da-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c08da-106">描述</span><span class="sxs-lookup"><span data-stu-id="c08da-106">Description</span></span>

<span data-ttu-id="c08da-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="c08da-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c08da-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c08da-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c08da-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="c08da-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c08da-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="c08da-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c08da-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="c08da-111">targets : 'T[]</span></span>

<span data-ttu-id="c08da-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c08da-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c08da-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c08da-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c08da-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="c08da-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c08da-115">不要</span><span class="sxs-lookup"><span data-stu-id="c08da-115">'T</span></span>

<span data-ttu-id="c08da-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="c08da-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c08da-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c08da-117">See Also</span></span>

- [<span data-ttu-id="c08da-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c08da-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c08da-119">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="c08da-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="c08da-120">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c08da-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)