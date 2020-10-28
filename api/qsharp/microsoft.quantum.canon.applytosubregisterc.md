---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699139"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="de3e7-102">ApplyToSubregisterC 操作</span><span class="sxs-lookup"><span data-stu-id="de3e7-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="de3e7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="de3e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="de3e7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de3e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de3e7-105">將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。</span><span class="sxs-lookup"><span data-stu-id="de3e7-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="de3e7-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="de3e7-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="de3e7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="de3e7-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="de3e7-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="de3e7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="de3e7-109">要套用至 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="de3e7-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="de3e7-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="de3e7-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="de3e7-111">索引的陣列，表示將套用作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="de3e7-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="de3e7-112">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de3e7-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="de3e7-113">註冊的作用。</span><span class="sxs-lookup"><span data-stu-id="de3e7-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de3e7-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de3e7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="de3e7-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="de3e7-115">See Also</span></span>

- [<span data-ttu-id="de3e7-116">Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="de3e7-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)