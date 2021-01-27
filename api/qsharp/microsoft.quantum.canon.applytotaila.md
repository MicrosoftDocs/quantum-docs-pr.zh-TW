---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841176"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="77504-102">ApplyToTailA 操作</span><span class="sxs-lookup"><span data-stu-id="77504-102">ApplyToTailA operation</span></span>

<span data-ttu-id="77504-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77504-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77504-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77504-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77504-105">將作業套用至陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="77504-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="77504-106">描述</span><span class="sxs-lookup"><span data-stu-id="77504-106">Description</span></span>

<span data-ttu-id="77504-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="77504-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="77504-108">輸入</span><span class="sxs-lookup"><span data-stu-id="77504-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="77504-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="77504-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="77504-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="77504-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="77504-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="77504-111">targets : 'T[]</span></span>

<span data-ttu-id="77504-112">目標的陣列，最後會將其套用至其中 `op` 。</span><span class="sxs-lookup"><span data-stu-id="77504-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77504-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77504-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77504-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="77504-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77504-115">不要</span><span class="sxs-lookup"><span data-stu-id="77504-115">'T</span></span>

<span data-ttu-id="77504-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="77504-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="77504-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="77504-117">See Also</span></span>

- [<span data-ttu-id="77504-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="77504-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="77504-119">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="77504-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="77504-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="77504-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)