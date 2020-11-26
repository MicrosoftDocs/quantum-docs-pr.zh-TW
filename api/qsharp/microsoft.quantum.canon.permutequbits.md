---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205596"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="0f282-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="0f282-102">PermuteQubits operation</span></span>

<span data-ttu-id="0f282-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f282-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f282-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f282-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f282-105">使用交換操作來 Permutes 量子位。</span><span class="sxs-lookup"><span data-stu-id="0f282-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0f282-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0f282-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="0f282-107">順序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0f282-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0f282-108">描述量子位的新順序，其中量子位 at index 現在會依序為 [i]。</span><span class="sxs-lookup"><span data-stu-id="0f282-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0f282-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f282-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f282-110">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="0f282-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f282-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f282-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

