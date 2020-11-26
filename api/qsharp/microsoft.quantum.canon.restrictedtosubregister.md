---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a49b15ac9c3ba9c1959bdead11549c1f37caabf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205366"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="ddd31-102">RestrictedToSubregister 函式</span><span class="sxs-lookup"><span data-stu-id="ddd31-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="ddd31-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ddd31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ddd31-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddd31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddd31-105">將作業限制為暫存器的索引陣列，亦即 subregister。</span><span class="sxs-lookup"><span data-stu-id="ddd31-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="ddd31-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ddd31-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="ddd31-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddd31-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ddd31-108">要限制為 subregister 的作業。</span><span class="sxs-lookup"><span data-stu-id="ddd31-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="ddd31-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ddd31-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ddd31-110">索引的陣列，表示將限制作業的量子位。</span><span class="sxs-lookup"><span data-stu-id="ddd31-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="ddd31-111">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddd31-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="ddd31-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ddd31-112">See Also</span></span>

- [<span data-ttu-id="ddd31-113">Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="ddd31-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="ddd31-114">Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="ddd31-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="ddd31-115">Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="ddd31-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)