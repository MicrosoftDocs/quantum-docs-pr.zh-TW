---
uid: Microsoft.Quantum.Canon.Delayed
title: 延遲函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699032"
---
# <a name="delayed-function"></a><span data-ttu-id="311ac-102">延遲函數</span><span class="sxs-lookup"><span data-stu-id="311ac-102">Delayed function</span></span>

<span data-ttu-id="311ac-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="311ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="311ac-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="311ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="311ac-105">傳回以指定的引數套用指定作業的作業。</span><span class="sxs-lookup"><span data-stu-id="311ac-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="311ac-106">輸入</span><span class="sxs-lookup"><span data-stu-id="311ac-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="311ac-107">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="311ac-107">op : 'T => 'U</span></span> 

<span data-ttu-id="311ac-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="311ac-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="311ac-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="311ac-109">arg : 'T</span></span>

<span data-ttu-id="311ac-110">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="311ac-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="311ac-111">Output： [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="311ac-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="311ac-112">適用于輸入的新作業 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="311ac-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="311ac-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="311ac-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="311ac-114">不要</span><span class="sxs-lookup"><span data-stu-id="311ac-114">'T</span></span>

<span data-ttu-id="311ac-115">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="311ac-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="311ac-116">' U</span><span class="sxs-lookup"><span data-stu-id="311ac-116">'U</span></span>

<span data-ttu-id="311ac-117">要延遲之作業的傳回型別。</span><span class="sxs-lookup"><span data-stu-id="311ac-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="311ac-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="311ac-118">See Also</span></span>

- [<span data-ttu-id="311ac-119">Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="311ac-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="311ac-120">Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="311ac-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="311ac-121">Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="311ac-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="311ac-122">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="311ac-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)