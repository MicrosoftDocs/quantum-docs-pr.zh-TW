---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697146"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="1f6d4-102">IntsToPaulis 函式</span><span class="sxs-lookup"><span data-stu-id="1f6d4-102">IntsToPaulis function</span></span>

<span data-ttu-id="1f6d4-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f6d4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f6d4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f6d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f6d4-105">將整數陣列轉換成單一量子位 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="1f6d4-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="1f6d4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1f6d4-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="1f6d4-107">int： [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f6d4-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f6d4-108">要轉換成 Pauli 運算子之範圍中的整數陣列 `0..3`  。</span><span class="sxs-lookup"><span data-stu-id="1f6d4-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="1f6d4-109">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1f6d4-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1f6d4-110">`paulis`Pauli 運算子 `Pauli[]` 的陣列，其長度等同 `ints` `paulis[idxPauli]` 于 `[PauliI, PauliX, PauliY, PauliZ]` 指定 `ints[idxPauli]` 的專案。</span><span class="sxs-lookup"><span data-stu-id="1f6d4-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>