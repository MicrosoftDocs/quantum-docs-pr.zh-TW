---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829286"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="f1ef2-102">DumpOperation 操作</span><span class="sxs-lookup"><span data-stu-id="f1ef2-102">DumpOperation operation</span></span>

<span data-ttu-id="f1ef2-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f1ef2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f1ef2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1ef2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1ef2-105">在指定作業的情況下，會顯示目前執行目標所提供之作業的相關診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="f1ef2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f1ef2-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f1ef2-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1ef2-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1ef2-108">給定作業作用所在的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="f1ef2-109">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="f1ef2-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f1ef2-110">要診斷的作業。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1ef2-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1ef2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f1ef2-112">範例</span><span class="sxs-lookup"><span data-stu-id="f1ef2-112">Example</span></span>

<span data-ttu-id="f1ef2-113">在量子模擬器目標上執行時，下列程式碼片段會輸出矩陣 $ $ \begin{aligned} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="f1ef2-114">備註</span><span class="sxs-lookup"><span data-stu-id="f1ef2-114">Remarks</span></span>

<span data-ttu-id="f1ef2-115">呼叫此作業不會從 Q # 內觀察到任何效果。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="f1ef2-116">顯示的確切診斷（如果有的話）取決於目前的執行目標和編輯器環境。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="f1ef2-117">例如，在完整狀態量子模擬器上使用時，會顯示用來表示的單一矩陣 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="f1ef2-118">請注意，在承認全域階段不明確的模擬器上執行時 (例如：完整狀態模擬器) ，傳回的標記法可能會因全域階段而異。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="f1ef2-119">同樣地，資料列和資料行矩陣表示的順序可能會與支援此作業的每個模擬器所使用的慣例不同。</span><span class="sxs-lookup"><span data-stu-id="f1ef2-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>