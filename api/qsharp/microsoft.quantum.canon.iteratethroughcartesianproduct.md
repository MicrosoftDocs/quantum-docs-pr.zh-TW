---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840270"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="faaa3-102">IterateThroughCartesianProduct 操作</span><span class="sxs-lookup"><span data-stu-id="faaa3-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="faaa3-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="faaa3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="faaa3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="faaa3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="faaa3-105">針對多個範圍的笛卡兒乘積中的每個索引套用作業。</span><span class="sxs-lookup"><span data-stu-id="faaa3-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="faaa3-106">描述</span><span class="sxs-lookup"><span data-stu-id="faaa3-106">Description</span></span>

<span data-ttu-id="faaa3-107">針對 `0..(bounds[0] - 1)` 、 `0..(bounds[1] - 1)` 、...、等笛卡兒乘積的每個元素反復套用作業 `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="faaa3-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="faaa3-108">輸入</span><span class="sxs-lookup"><span data-stu-id="faaa3-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="faaa3-109">界限： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="faaa3-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="faaa3-110">陣列，指定要反復查看的範圍，並將每個範圍指定為整數長度。</span><span class="sxs-lookup"><span data-stu-id="faaa3-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="faaa3-111">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="faaa3-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="faaa3-112">針對給定笛卡兒乘積的每個專案呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="faaa3-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="faaa3-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="faaa3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="faaa3-114">範例</span><span class="sxs-lookup"><span data-stu-id="faaa3-114">Example</span></span>

<span data-ttu-id="faaa3-115">在指定作業 `op` 的情況下，下列兩個程式碼片段是相等的：</span><span class="sxs-lookup"><span data-stu-id="faaa3-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="faaa3-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="faaa3-116">See Also</span></span>

- [<span data-ttu-id="faaa3-117">Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="faaa3-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)