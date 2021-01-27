---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847609"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="21223-102">_DeltaParityCNOTbitstring 函式</span><span class="sxs-lookup"><span data-stu-id="21223-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="21223-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="21223-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="21223-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="21223-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="21223-105">的傳統處理步驟 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="21223-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="21223-106">這會計算用來評估任何兩個 PQRS 之間的同位差異的控制項量子位清單 .。。偶數長度的詞彙。</span><span class="sxs-lookup"><span data-stu-id="21223-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="21223-107">輸入</span><span class="sxs-lookup"><span data-stu-id="21223-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="21223-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="21223-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="21223-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="21223-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="21223-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="21223-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="21223-111">備註</span><span class="sxs-lookup"><span data-stu-id="21223-111">Remarks</span></span>

<span data-ttu-id="21223-112">這假設詞彙的長度是偶數。</span><span class="sxs-lookup"><span data-stu-id="21223-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="21223-113">針對任何兩個詞彙之間的同位差異，計算控制項清單。</span><span class="sxs-lookup"><span data-stu-id="21223-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="21223-114">這會假設輸入清單是以遞增順序排序。</span><span class="sxs-lookup"><span data-stu-id="21223-114">This assumes that the input lists is sorted in ascending order.</span></span>