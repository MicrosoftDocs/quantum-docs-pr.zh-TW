---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698919"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="fbc22-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="fbc22-102">PermuteQubits operation</span></span>

<span data-ttu-id="fbc22-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbc22-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbc22-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbc22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbc22-105">使用交換操作來 Permutes 量子位。</span><span class="sxs-lookup"><span data-stu-id="fbc22-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fbc22-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fbc22-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="fbc22-107">順序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fbc22-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fbc22-108">描述量子位的新順序，其中量子位 at index 現在會依序為 [i]。</span><span class="sxs-lookup"><span data-stu-id="fbc22-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fbc22-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fbc22-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fbc22-110">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="fbc22-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbc22-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbc22-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

