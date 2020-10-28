---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699142"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="7cde6-102">ApplyToSubregisterA 操作</span><span class="sxs-lookup"><span data-stu-id="7cde6-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="7cde6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7cde6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7cde6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7cde6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7cde6-105">將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。</span><span class="sxs-lookup"><span data-stu-id="7cde6-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="7cde6-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7cde6-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7cde6-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7cde6-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="7cde6-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="7cde6-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7cde6-109">要套用至 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="7cde6-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="7cde6-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7cde6-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7cde6-111">索引的陣列，表示將套用作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="7cde6-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7cde6-112">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7cde6-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7cde6-113">註冊的作用。</span><span class="sxs-lookup"><span data-stu-id="7cde6-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7cde6-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cde6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7cde6-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7cde6-115">See Also</span></span>

- [<span data-ttu-id="7cde6-116">Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="7cde6-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)