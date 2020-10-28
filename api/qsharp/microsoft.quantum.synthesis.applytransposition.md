---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701078"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="0ef1d-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="0ef1d-102">ApplyTransposition operation</span></span>

<span data-ttu-id="0ef1d-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0ef1d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="0ef1d-105">描述</span><span class="sxs-lookup"><span data-stu-id="0ef1d-105">Description</span></span>

<span data-ttu-id="0ef1d-106">這項作業會以指定的 `a` `b` 狀態向量（長度為 $n $），將索引中的波幅交換至索引的波幅 `register` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1d-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="0ef1d-107">如果 `a` 等於 `b` ，則不會變更狀態向量。</span><span class="sxs-lookup"><span data-stu-id="0ef1d-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="0ef1d-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0ef1d-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0ef1d-109">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ef1d-110">第一個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="0ef1d-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="0ef1d-111">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ef1d-112">第二個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="0ef1d-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0ef1d-113">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0ef1d-114">要套用調換的 $n $ 量子位清單。</span><span class="sxs-lookup"><span data-stu-id="0ef1d-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ef1d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ef1d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

