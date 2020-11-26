---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206471"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="c2d47-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="c2d47-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="c2d47-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2d47-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2d47-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2d47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2d47-105">在整數範圍的笛卡兒乘冪中，為每個索引套用一個運算。</span><span class="sxs-lookup"><span data-stu-id="c2d47-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="c2d47-106">描述</span><span class="sxs-lookup"><span data-stu-id="c2d47-106">Description</span></span>

<span data-ttu-id="c2d47-107">反復針對範圍的笛卡兒乘冪的每個元素，套用一項作業 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="c2d47-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="c2d47-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c2d47-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="c2d47-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2d47-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2d47-110">應產生範圍的笛卡兒乘冪 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="c2d47-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="c2d47-111">系結： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2d47-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2d47-112">要逐一查看的範圍規格，指定為範圍的長度。</span><span class="sxs-lookup"><span data-stu-id="c2d47-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="c2d47-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2d47-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2d47-114">針對給定笛卡兒乘冪的每個元素呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="c2d47-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2d47-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2d47-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c2d47-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c2d47-116">See Also</span></span>

- [<span data-ttu-id="c2d47-117">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="c2d47-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)