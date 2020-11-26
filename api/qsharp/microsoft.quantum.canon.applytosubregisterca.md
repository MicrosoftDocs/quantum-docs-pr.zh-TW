---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a5ebfb17b1e66bd509f3a562f852986c83d0fef0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208001"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="edbc7-102">ApplyToSubregisterCA 操作</span><span class="sxs-lookup"><span data-stu-id="edbc7-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="edbc7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="edbc7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="edbc7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edbc7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edbc7-105">將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。</span><span class="sxs-lookup"><span data-stu-id="edbc7-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="edbc7-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="edbc7-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="edbc7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="edbc7-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="edbc7-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="edbc7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edbc7-109">要套用至 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="edbc7-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="edbc7-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="edbc7-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="edbc7-111">索引的陣列，表示將套用作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="edbc7-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="edbc7-112">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="edbc7-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="edbc7-113">註冊的作用。</span><span class="sxs-lookup"><span data-stu-id="edbc7-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="edbc7-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="edbc7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="edbc7-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="edbc7-115">See Also</span></span>

- [<span data-ttu-id="edbc7-116">Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="edbc7-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)