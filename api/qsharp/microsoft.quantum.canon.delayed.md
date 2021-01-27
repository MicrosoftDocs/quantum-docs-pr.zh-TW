---
uid: Microsoft.Quantum.Canon.Delayed
title: 延遲函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840576"
---
# <a name="delayed-function"></a><span data-ttu-id="c142d-102">延遲函數</span><span class="sxs-lookup"><span data-stu-id="c142d-102">Delayed function</span></span>

<span data-ttu-id="c142d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c142d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c142d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c142d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c142d-105">傳回以指定的引數套用指定作業的作業。</span><span class="sxs-lookup"><span data-stu-id="c142d-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="c142d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c142d-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="c142d-107">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="c142d-107">op : 'T => 'U</span></span> 

<span data-ttu-id="c142d-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="c142d-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="c142d-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="c142d-109">arg : 'T</span></span>

<span data-ttu-id="c142d-110">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="c142d-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="c142d-111">Output： [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="c142d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="c142d-112">適用于輸入的新作業 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="c142d-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c142d-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c142d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c142d-114">不要</span><span class="sxs-lookup"><span data-stu-id="c142d-114">'T</span></span>

<span data-ttu-id="c142d-115">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="c142d-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="c142d-116">' U</span><span class="sxs-lookup"><span data-stu-id="c142d-116">'U</span></span>

<span data-ttu-id="c142d-117">要延遲之作業的傳回型別。</span><span class="sxs-lookup"><span data-stu-id="c142d-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c142d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c142d-118">See Also</span></span>

- [<span data-ttu-id="c142d-119">Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="c142d-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="c142d-120">Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="c142d-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="c142d-121">Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="c142d-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="c142d-122">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="c142d-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)