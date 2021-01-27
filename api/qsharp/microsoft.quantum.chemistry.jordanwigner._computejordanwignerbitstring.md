---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839537"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="b52f7-102">_ComputeJordanWignerBitString 函式</span><span class="sxs-lookup"><span data-stu-id="b52f7-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="b52f7-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b52f7-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b52f7-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b52f7-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b52f7-105">以偶數的建立/annihilation 運算子數目，計算 fermionic 運算子中 fermion 索引之間的約旦 Wigner 字串 Z 元件。</span><span class="sxs-lookup"><span data-stu-id="b52f7-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b52f7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b52f7-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="b52f7-107">nFermions： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b52f7-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b52f7-108">系統中的 fermions 數目。</span><span class="sxs-lookup"><span data-stu-id="b52f7-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="b52f7-109">idxFermions： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b52f7-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b52f7-110">fermionic 運算子索引。</span><span class="sxs-lookup"><span data-stu-id="b52f7-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b52f7-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b52f7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b52f7-112">`Bool[]` `true` 應該套用的 Bitstring `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="b52f7-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="b52f7-113">範例</span><span class="sxs-lookup"><span data-stu-id="b52f7-113">Example</span></span>

<span data-ttu-id="b52f7-114">let bitString = _ComputeJordanWignerBitString (6，[0，1，2，6] ) ;bitString 是 [false，false，false，true，true，true，false]。</span><span class="sxs-lookup"><span data-stu-id="b52f7-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>