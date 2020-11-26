---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202051"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="44145-102">DumpOperation 操作</span><span class="sxs-lookup"><span data-stu-id="44145-102">DumpOperation operation</span></span>

<span data-ttu-id="44145-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="44145-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="44145-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44145-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44145-105">在指定作業的情況下，會顯示目前執行目標所提供之作業的相關診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="44145-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="44145-106">輸入</span><span class="sxs-lookup"><span data-stu-id="44145-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="44145-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44145-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44145-108">給定作業作用所在的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="44145-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="44145-109">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="44145-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="44145-110">要診斷的作業。</span><span class="sxs-lookup"><span data-stu-id="44145-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44145-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44145-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="44145-112">備註</span><span class="sxs-lookup"><span data-stu-id="44145-112">Remarks</span></span>

<span data-ttu-id="44145-113">呼叫此作業不會從 Q # 內觀察到任何效果。</span><span class="sxs-lookup"><span data-stu-id="44145-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="44145-114">顯示的確切診斷（如果有的話）取決於目前的執行目標和編輯器環境。</span><span class="sxs-lookup"><span data-stu-id="44145-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="44145-115">例如，在完整狀態量子模擬器上使用時，會顯示用來表示的單一矩陣 `op` 。</span><span class="sxs-lookup"><span data-stu-id="44145-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="44145-116">請注意，在承認全域階段不明確的模擬器上執行時 (例如：完整狀態模擬器) ，傳回的標記法可能會因全域階段而異。</span><span class="sxs-lookup"><span data-stu-id="44145-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="44145-117">同樣地，資料列和資料行矩陣表示的順序可能會與支援此作業的每個模擬器所使用的慣例不同。</span><span class="sxs-lookup"><span data-stu-id="44145-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>