---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226072"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="bfd6b-102">_DeltaParityCNOTbitstring 函式</span><span class="sxs-lookup"><span data-stu-id="bfd6b-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="bfd6b-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="bfd6b-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="bfd6b-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="bfd6b-105">的傳統處理步驟 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="bfd6b-106">這會計算用來評估任何兩個 PQRS 之間的同位差異的控制項量子位清單 .。。偶數長度的詞彙。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="bfd6b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bfd6b-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="bfd6b-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bfd6b-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="bfd6b-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bfd6b-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="bfd6b-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="bfd6b-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="bfd6b-111">備註</span><span class="sxs-lookup"><span data-stu-id="bfd6b-111">Remarks</span></span>

<span data-ttu-id="bfd6b-112">這假設詞彙的長度是偶數。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="bfd6b-113">針對任何兩個詞彙之間的同位差異，計算控制項清單。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="bfd6b-114">這會假設輸入清單是以遞增順序排序。</span><span class="sxs-lookup"><span data-stu-id="bfd6b-114">This assumes that the input lists is sorted in ascending order.</span></span>