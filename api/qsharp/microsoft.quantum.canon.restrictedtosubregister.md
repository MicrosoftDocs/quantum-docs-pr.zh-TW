---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698886"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="27d3c-102">RestrictedToSubregister 函式</span><span class="sxs-lookup"><span data-stu-id="27d3c-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="27d3c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27d3c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27d3c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27d3c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27d3c-105">將作業限制為暫存器的索引陣列，亦即 subregister。</span><span class="sxs-lookup"><span data-stu-id="27d3c-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="27d3c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="27d3c-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="27d3c-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27d3c-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="27d3c-108">要限制為 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="27d3c-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="27d3c-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="27d3c-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="27d3c-110">索引的陣列，表示將限制作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="27d3c-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="27d3c-111">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27d3c-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="27d3c-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="27d3c-112">See Also</span></span>

- [<span data-ttu-id="27d3c-113">Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="27d3c-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="27d3c-114">Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="27d3c-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="27d3c-115">Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="27d3c-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)