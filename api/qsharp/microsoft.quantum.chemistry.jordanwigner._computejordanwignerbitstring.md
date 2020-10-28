---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698646"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="b8a3f-102">_ComputeJordanWignerBitString 函式</span><span class="sxs-lookup"><span data-stu-id="b8a3f-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="b8a3f-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b8a3f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b8a3f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8a3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8a3f-105">以偶數的建立/annihilation 運算子數目，計算 fermionic 運算子中 fermion 索引之間的約旦 Wigner 字串 Z 元件。</span><span class="sxs-lookup"><span data-stu-id="b8a3f-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b8a3f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b8a3f-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="b8a3f-107">nFermions： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8a3f-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8a3f-108">系統中的 fermions 數目。</span><span class="sxs-lookup"><span data-stu-id="b8a3f-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="b8a3f-109">idxFermions： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b8a3f-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b8a3f-110">fermionic 運算子索引。</span><span class="sxs-lookup"><span data-stu-id="b8a3f-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b8a3f-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b8a3f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b8a3f-112">`Bool[]` `true` 應該套用的 Bitstring `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="b8a3f-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>