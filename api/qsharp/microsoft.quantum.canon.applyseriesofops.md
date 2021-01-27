---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841505"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="6c09d-102">ApplySeriesOfOps 操作</span><span class="sxs-lookup"><span data-stu-id="6c09d-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="6c09d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c09d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c09d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c09d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c09d-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="6c09d-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6c09d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6c09d-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="6c09d-107">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="6c09d-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="6c09d-108">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="6c09d-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="6c09d-109">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="6c09d-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="6c09d-110">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6c09d-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6c09d-111">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="6c09d-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6c09d-112">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="6c09d-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="6c09d-113">register： t []</span><span class="sxs-lookup"><span data-stu-id="6c09d-113">register : 'T[]</span></span>

<span data-ttu-id="6c09d-114">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="6c09d-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c09d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c09d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6c09d-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="6c09d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c09d-117">不要</span><span class="sxs-lookup"><span data-stu-id="6c09d-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="6c09d-118">範例</span><span class="sxs-lookup"><span data-stu-id="6c09d-118">Example</span></span>

<span data-ttu-id="6c09d-119">下列適用于 Exp ( [PauliX，PauliY]，0.5) 至量子位0、1//then X 至量子位 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubit (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOps (ops、索引、qubitArray) ;</span><span class="sxs-lookup"><span data-stu-id="6c09d-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="6c09d-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6c09d-120">See Also</span></span>

- [<span data-ttu-id="6c09d-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6c09d-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)