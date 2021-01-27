---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850479"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="44119-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="44119-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="44119-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44119-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44119-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44119-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44119-105">將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。</span><span class="sxs-lookup"><span data-stu-id="44119-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="44119-106">輸入</span><span class="sxs-lookup"><span data-stu-id="44119-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="44119-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44119-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="44119-108">要套用至 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="44119-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="44119-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="44119-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="44119-110">索引的陣列，表示將套用作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="44119-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="44119-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44119-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44119-112">註冊的作用。</span><span class="sxs-lookup"><span data-stu-id="44119-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44119-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44119-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="44119-114">範例</span><span class="sxs-lookup"><span data-stu-id="44119-114">Example</span></span>

<span data-ttu-id="44119-115">建立三個量子位狀態 $ \frac {1} {\sqrt {2} } \ket {0} \_ 2 ( \ket {0} \_ 1 \ ket {0} _3 + \ket {1} \_ 1 \ ket {1} _3) $：</span><span class="sxs-lookup"><span data-stu-id="44119-115">Create three qubit state $\frac{1}{\sqrt{2}}\ket{0}\_2(\ket{0}\_1\ket{0}_3+\ket{1}\_1\ket{1}_3)$:</span></span>

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a><span data-ttu-id="44119-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="44119-116">See Also</span></span>

- [<span data-ttu-id="44119-117">Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="44119-117">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="44119-118">Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="44119-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="44119-119">Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="44119-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)