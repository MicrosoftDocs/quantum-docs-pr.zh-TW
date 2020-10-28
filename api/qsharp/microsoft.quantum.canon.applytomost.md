---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699171"
---
# <a name="applytomost-operation"></a><span data-ttu-id="93459-102">ApplyToMost 操作</span><span class="sxs-lookup"><span data-stu-id="93459-102">ApplyToMost operation</span></span>

<span data-ttu-id="93459-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93459-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93459-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93459-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93459-105">將作業套用至陣列的最後一個元素以外的所有專案。</span><span class="sxs-lookup"><span data-stu-id="93459-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="93459-106">描述</span><span class="sxs-lookup"><span data-stu-id="93459-106">Description</span></span>

<span data-ttu-id="93459-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="93459-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="93459-108">輸入</span><span class="sxs-lookup"><span data-stu-id="93459-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="93459-109">op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93459-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="93459-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="93459-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="93459-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="93459-111">targets : 'T[]</span></span>

<span data-ttu-id="93459-112">目標的陣列，其中最後一個只會套用到最後一個 `op` 。</span><span class="sxs-lookup"><span data-stu-id="93459-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93459-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93459-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93459-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="93459-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93459-115">不要</span><span class="sxs-lookup"><span data-stu-id="93459-115">'T</span></span>

<span data-ttu-id="93459-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="93459-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="93459-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93459-117">See Also</span></span>

- [<span data-ttu-id="93459-118">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="93459-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="93459-119">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="93459-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="93459-120">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="93459-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)