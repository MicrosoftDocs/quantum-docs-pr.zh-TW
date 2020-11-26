---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203309"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="00aa6-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="00aa6-102">ApplyTransposition operation</span></span>

<span data-ttu-id="00aa6-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="00aa6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="00aa6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00aa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="00aa6-105">描述</span><span class="sxs-lookup"><span data-stu-id="00aa6-105">Description</span></span>

<span data-ttu-id="00aa6-106">這項作業會以指定的 `a` `b` 狀態向量（長度為 $n $），將索引中的波幅交換至索引的波幅 `register` 。</span><span class="sxs-lookup"><span data-stu-id="00aa6-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="00aa6-107">如果 `a` 等於 `b` ，則不會變更狀態向量。</span><span class="sxs-lookup"><span data-stu-id="00aa6-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="00aa6-108">輸入</span><span class="sxs-lookup"><span data-stu-id="00aa6-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="00aa6-109">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00aa6-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00aa6-110">第一個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="00aa6-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="00aa6-111">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00aa6-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00aa6-112">第二個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="00aa6-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="00aa6-113">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="00aa6-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="00aa6-114">要套用調換的 $n $ 量子位清單。</span><span class="sxs-lookup"><span data-stu-id="00aa6-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00aa6-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00aa6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

