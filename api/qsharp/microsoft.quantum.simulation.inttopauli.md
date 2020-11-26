---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229200"
---
# <a name="inttopauli-function"></a><span data-ttu-id="f6b0b-102">IntToPauli 函式</span><span class="sxs-lookup"><span data-stu-id="f6b0b-102">IntToPauli function</span></span>

<span data-ttu-id="f6b0b-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f6b0b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f6b0b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6b0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6b0b-105">將整數轉換成單一量子位的 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="f6b0b-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="f6b0b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f6b0b-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="f6b0b-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6b0b-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f6b0b-108">`0..3`要轉換成 Pauli 運算子的範圍中的整數。</span><span class="sxs-lookup"><span data-stu-id="f6b0b-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="f6b0b-109">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f6b0b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f6b0b-110">`Pauli`提供的運算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。</span><span class="sxs-lookup"><span data-stu-id="f6b0b-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>