---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697546"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="7379e-102">_DeltaParityCNOTbitstring 函式</span><span class="sxs-lookup"><span data-stu-id="7379e-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="7379e-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="7379e-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7379e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7379e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7379e-105">的傳統處理步驟 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="7379e-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="7379e-106">這會計算用來評估任何兩個 PQRS 之間的同位差異的控制項量子位清單 .。。偶數長度的詞彙。</span><span class="sxs-lookup"><span data-stu-id="7379e-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="7379e-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7379e-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="7379e-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7379e-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="7379e-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7379e-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="7379e-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="7379e-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="7379e-111">備註</span><span class="sxs-lookup"><span data-stu-id="7379e-111">Remarks</span></span>

<span data-ttu-id="7379e-112">這假設詞彙的長度是偶數。</span><span class="sxs-lookup"><span data-stu-id="7379e-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="7379e-113">針對任何兩個詞彙之間的同位差異，計算控制項清單。</span><span class="sxs-lookup"><span data-stu-id="7379e-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="7379e-114">這會假設輸入清單是以遞增順序排序。</span><span class="sxs-lookup"><span data-stu-id="7379e-114">This assumes that the input lists is sorted in ascending order.</span></span>