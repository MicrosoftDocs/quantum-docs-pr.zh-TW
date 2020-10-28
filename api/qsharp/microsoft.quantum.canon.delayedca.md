---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699027"
---
# <a name="delayedca-function"></a><span data-ttu-id="84679-102">DelayedCA 函式</span><span class="sxs-lookup"><span data-stu-id="84679-102">DelayedCA function</span></span>

<span data-ttu-id="84679-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84679-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84679-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84679-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84679-105">傳回以指定的引數套用指定作業的作業。</span><span class="sxs-lookup"><span data-stu-id="84679-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="84679-106">輸入</span><span class="sxs-lookup"><span data-stu-id="84679-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="84679-107">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="84679-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="84679-108">套用傳回值的結果所要套用的作業</span><span class="sxs-lookup"><span data-stu-id="84679-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="84679-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="84679-109">arg : 'T</span></span>

<span data-ttu-id="84679-110">要套用作業的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="84679-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="84679-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="84679-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="84679-112">適用于輸入的新作業 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="84679-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84679-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="84679-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84679-114">不要</span><span class="sxs-lookup"><span data-stu-id="84679-114">'T</span></span>

<span data-ttu-id="84679-115">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="84679-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="84679-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="84679-116">See Also</span></span>

- [<span data-ttu-id="84679-117">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="84679-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="84679-118">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="84679-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)