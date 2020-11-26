---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: ApplyOpRepeatedlyOverA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 65675a3a83f0ac730b9e3a58f80f77c096c1ce57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209140"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="f9686-102">ApplyOpRepeatedlyOverA 操作</span><span class="sxs-lookup"><span data-stu-id="f9686-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="f9686-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9686-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9686-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9686-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9686-105">將相同的 op 套用至量子位登錄多次。</span><span class="sxs-lookup"><span data-stu-id="f9686-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f9686-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f9686-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="f9686-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="f9686-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f9686-108">要在量子位暫存器上多次套用的作業</span><span class="sxs-lookup"><span data-stu-id="f9686-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="f9686-109">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="f9686-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="f9686-110">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="f9686-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="f9686-111">每個陣列都應該包含描述要使用之量子位的整數清單。</span><span class="sxs-lookup"><span data-stu-id="f9686-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f9686-112">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f9686-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f9686-113">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="f9686-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9686-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9686-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f9686-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9686-115">See Also</span></span>

- [<span data-ttu-id="f9686-116">Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="f9686-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)