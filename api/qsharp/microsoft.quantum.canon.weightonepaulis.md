---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851978"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="e5271-102">WeightOnePaulis 函式</span><span class="sxs-lookup"><span data-stu-id="e5271-102">WeightOnePaulis function</span></span>

<span data-ttu-id="e5271-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e5271-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e5271-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5271-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5271-105">傳回指定量子位數目之所有加權 1 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="e5271-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="e5271-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e5271-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e5271-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5271-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5271-108">用來定義所傳回 Pauli 運算子的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="e5271-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e5271-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="e5271-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="e5271-110">多量子位 Pauli 運算子的陣列，其中每個運算子都會表示為具有長度的陣列 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="e5271-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>