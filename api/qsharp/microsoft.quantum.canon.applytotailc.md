---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699134"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="d9b43-102">ApplyToTailC 操作</span><span class="sxs-lookup"><span data-stu-id="d9b43-102">ApplyToTailC operation</span></span>

<span data-ttu-id="d9b43-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9b43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9b43-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9b43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9b43-105">將作業套用至陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="d9b43-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d9b43-106">描述</span><span class="sxs-lookup"><span data-stu-id="d9b43-106">Description</span></span>

<span data-ttu-id="d9b43-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="d9b43-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d9b43-108">輸入</span><span class="sxs-lookup"><span data-stu-id="d9b43-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="d9b43-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="d9b43-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d9b43-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="d9b43-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d9b43-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="d9b43-111">targets : 'T[]</span></span>

<span data-ttu-id="d9b43-112">目標的陣列，最後會將其套用至其中 `op` 。</span><span class="sxs-lookup"><span data-stu-id="d9b43-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9b43-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9b43-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d9b43-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="d9b43-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9b43-115">不要</span><span class="sxs-lookup"><span data-stu-id="d9b43-115">'T</span></span>

<span data-ttu-id="d9b43-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="d9b43-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b43-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9b43-117">See Also</span></span>

- [<span data-ttu-id="d9b43-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="d9b43-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="d9b43-119">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="d9b43-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="d9b43-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="d9b43-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)