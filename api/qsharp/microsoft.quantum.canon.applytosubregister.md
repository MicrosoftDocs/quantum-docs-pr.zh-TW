---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208103"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="878ee-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="878ee-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="878ee-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="878ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="878ee-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="878ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="878ee-105">將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。</span><span class="sxs-lookup"><span data-stu-id="878ee-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="878ee-106">輸入</span><span class="sxs-lookup"><span data-stu-id="878ee-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="878ee-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="878ee-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="878ee-108">要套用至 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="878ee-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="878ee-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="878ee-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="878ee-110">索引的陣列，表示將套用作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="878ee-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="878ee-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="878ee-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="878ee-112">註冊的作用。</span><span class="sxs-lookup"><span data-stu-id="878ee-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="878ee-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="878ee-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="878ee-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="878ee-114">See Also</span></span>

- [<span data-ttu-id="878ee-115">Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="878ee-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="878ee-116">Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="878ee-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="878ee-117">Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="878ee-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)