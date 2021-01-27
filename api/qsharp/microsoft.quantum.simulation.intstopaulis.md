---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842230"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="e2be8-102">IntsToPaulis 函式</span><span class="sxs-lookup"><span data-stu-id="e2be8-102">IntsToPaulis function</span></span>

<span data-ttu-id="e2be8-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e2be8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e2be8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2be8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2be8-105">將整數陣列轉換成單一量子位 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="e2be8-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="e2be8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e2be8-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="e2be8-107">int： [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e2be8-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e2be8-108">要轉換成 Pauli 運算子之範圍中的整數陣列 `0..3`  。</span><span class="sxs-lookup"><span data-stu-id="e2be8-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e2be8-109">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e2be8-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e2be8-110">`paulis`Pauli 運算子 `Pauli[]` 的陣列，其長度等同 `ints` `paulis[idxPauli]` 于 `[PauliI, PauliX, PauliY, PauliZ]` 指定 `ints[idxPauli]` 的專案。</span><span class="sxs-lookup"><span data-stu-id="e2be8-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>