---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844658"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="c3ccf-102">ApplySeriesOfOpsA 操作</span><span class="sxs-lookup"><span data-stu-id="c3ccf-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="c3ccf-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3ccf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3ccf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3ccf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3ccf-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="c3ccf-106"> (Adjoint) </span><span class="sxs-lookup"><span data-stu-id="c3ccf-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c3ccf-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c3ccf-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="c3ccf-108">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 []</span><span class="sxs-lookup"><span data-stu-id="c3ccf-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="c3ccf-109">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="c3ccf-110">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="c3ccf-111">每個都必須有 adjoint 仿函數</span><span class="sxs-lookup"><span data-stu-id="c3ccf-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="c3ccf-112">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="c3ccf-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="c3ccf-113">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="c3ccf-114">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="c3ccf-115">register： t []</span><span class="sxs-lookup"><span data-stu-id="c3ccf-115">register : 'T[]</span></span>

<span data-ttu-id="c3ccf-116">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="c3ccf-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3ccf-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3ccf-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3ccf-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="c3ccf-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3ccf-119">不要</span><span class="sxs-lookup"><span data-stu-id="c3ccf-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="c3ccf-120">範例</span><span class="sxs-lookup"><span data-stu-id="c3ccf-120">Example</span></span>

<span data-ttu-id="c3ccf-121">下列適用于 Exp ( [PauliX，PauliY]，0.5) 至量子位0、1//then X 至量子位 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubitA (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOpsA (ops、索引、qubitArray) ;</span><span class="sxs-lookup"><span data-stu-id="c3ccf-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="c3ccf-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3ccf-122">See Also</span></span>

- [<span data-ttu-id="c3ccf-123">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="c3ccf-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)