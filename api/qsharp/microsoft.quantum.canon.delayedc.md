---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207002"
---
# <a name="delayedc-function"></a><span data-ttu-id="9d2ab-102">DelayedC 函式</span><span class="sxs-lookup"><span data-stu-id="9d2ab-102">DelayedC function</span></span>

<span data-ttu-id="9d2ab-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d2ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d2ab-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d2ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d2ab-105">傳回以指定的引數套用指定作業的作業。</span><span class="sxs-lookup"><span data-stu-id="9d2ab-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="9d2ab-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9d2ab-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="9d2ab-107">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="9d2ab-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9d2ab-108">套用傳回值的結果所要套用的作業</span><span class="sxs-lookup"><span data-stu-id="9d2ab-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="9d2ab-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="9d2ab-109">arg : 'T</span></span>

<span data-ttu-id="9d2ab-110">要套用作業的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="9d2ab-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="9d2ab-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="9d2ab-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9d2ab-112">適用于輸入的新作業 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="9d2ab-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9d2ab-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="9d2ab-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d2ab-114">不要</span><span class="sxs-lookup"><span data-stu-id="9d2ab-114">'T</span></span>

<span data-ttu-id="9d2ab-115">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="9d2ab-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d2ab-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d2ab-116">See Also</span></span>

- [<span data-ttu-id="9d2ab-117">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="9d2ab-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="9d2ab-118">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="9d2ab-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)