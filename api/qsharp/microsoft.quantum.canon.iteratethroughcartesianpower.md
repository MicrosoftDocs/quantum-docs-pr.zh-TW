---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840287"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="4b874-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="4b874-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="4b874-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b874-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b874-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b874-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b874-105">在整數範圍的笛卡兒乘冪中，為每個索引套用一個運算。</span><span class="sxs-lookup"><span data-stu-id="4b874-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="4b874-106">描述</span><span class="sxs-lookup"><span data-stu-id="4b874-106">Description</span></span>

<span data-ttu-id="4b874-107">反復針對範圍的笛卡兒乘冪的每個元素，套用一項作業 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="4b874-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="4b874-108">輸入</span><span class="sxs-lookup"><span data-stu-id="4b874-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="4b874-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b874-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b874-110">應產生範圍的笛卡兒乘冪 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="4b874-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="4b874-111">系結： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b874-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b874-112">要逐一查看的範圍規格，指定為範圍的長度。</span><span class="sxs-lookup"><span data-stu-id="4b874-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="4b874-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b874-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4b874-114">針對給定笛卡兒乘冪的每個元素呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="4b874-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b874-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b874-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="4b874-116">範例</span><span class="sxs-lookup"><span data-stu-id="4b874-116">Example</span></span>

<span data-ttu-id="4b874-117">在指定作業 `op` 的情況下，下列兩個程式碼片段是相等的：</span><span class="sxs-lookup"><span data-stu-id="4b874-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="4b874-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4b874-118">See Also</span></span>

- [<span data-ttu-id="4b874-119">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="4b874-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)