---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698787"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="bad9a-102">WeightOnePaulis 函式</span><span class="sxs-lookup"><span data-stu-id="bad9a-102">WeightOnePaulis function</span></span>

<span data-ttu-id="bad9a-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bad9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bad9a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bad9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bad9a-105">傳回指定量子位數目之所有加權 1 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="bad9a-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="bad9a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bad9a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="bad9a-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bad9a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bad9a-108">用來定義所傳回 Pauli 運算子的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="bad9a-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="bad9a-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="bad9a-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="bad9a-110">多量子位 Pauli 運算子的陣列，其中每個運算子都會表示為具有長度的陣列 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="bad9a-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>