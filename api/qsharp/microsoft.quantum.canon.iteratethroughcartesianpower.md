---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698999"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="71067-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="71067-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="71067-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71067-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71067-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71067-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71067-105">在整數範圍的笛卡兒乘冪中，為每個索引套用一個運算。</span><span class="sxs-lookup"><span data-stu-id="71067-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="71067-106">描述</span><span class="sxs-lookup"><span data-stu-id="71067-106">Description</span></span>

<span data-ttu-id="71067-107">反復針對範圍的笛卡兒乘冪的每個元素，套用一項作業 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="71067-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="71067-108">輸入</span><span class="sxs-lookup"><span data-stu-id="71067-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="71067-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71067-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71067-110">應產生範圍的笛卡兒乘冪 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="71067-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="71067-111">系結： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71067-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71067-112">要逐一查看的範圍規格，指定為範圍的長度。</span><span class="sxs-lookup"><span data-stu-id="71067-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="71067-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71067-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="71067-114">針對給定笛卡兒乘冪的每個元素呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="71067-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71067-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71067-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="71067-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="71067-116">See Also</span></span>

- [<span data-ttu-id="71067-117">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="71067-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)