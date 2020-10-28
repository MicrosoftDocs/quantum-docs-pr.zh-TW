---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698119"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="71018-102">DumpOperation 操作</span><span class="sxs-lookup"><span data-stu-id="71018-102">DumpOperation operation</span></span>

<span data-ttu-id="71018-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71018-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71018-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71018-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71018-105">在指定作業的情況下，會顯示目前執行目標所提供之作業的相關診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="71018-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="71018-106">輸入</span><span class="sxs-lookup"><span data-stu-id="71018-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="71018-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71018-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71018-108">給定作業作用所在的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="71018-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="71018-109">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="71018-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71018-110">要診斷的作業。</span><span class="sxs-lookup"><span data-stu-id="71018-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71018-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71018-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="71018-112">備註</span><span class="sxs-lookup"><span data-stu-id="71018-112">Remarks</span></span>

<span data-ttu-id="71018-113">呼叫此作業不會從 Q # 內觀察到任何效果。</span><span class="sxs-lookup"><span data-stu-id="71018-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="71018-114">顯示的確切診斷（如果有的話）取決於目前的執行目標和編輯器環境。</span><span class="sxs-lookup"><span data-stu-id="71018-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="71018-115">例如，在完整狀態量子模擬器上使用時，會顯示用來表示的單一矩陣 `op` 。</span><span class="sxs-lookup"><span data-stu-id="71018-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="71018-116">請注意，在承認全域階段不明確的模擬器上執行時 (例如：完整狀態模擬器) ，傳回的標記法可能會因全域階段而異。</span><span class="sxs-lookup"><span data-stu-id="71018-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="71018-117">同樣地，資料列和資料行矩陣表示的順序可能會與支援此作業的每個模擬器所使用的慣例不同。</span><span class="sxs-lookup"><span data-stu-id="71018-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>