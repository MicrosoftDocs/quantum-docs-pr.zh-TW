---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700959"
---
# <a name="inttopauli-function"></a><span data-ttu-id="56184-102">IntToPauli 函式</span><span class="sxs-lookup"><span data-stu-id="56184-102">IntToPauli function</span></span>

<span data-ttu-id="56184-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="56184-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="56184-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56184-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56184-105">將整數轉換成單一量子位的 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="56184-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="56184-106">輸入</span><span class="sxs-lookup"><span data-stu-id="56184-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="56184-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56184-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56184-108">`0..3`要轉換成 Pauli 運算子的範圍中的整數。</span><span class="sxs-lookup"><span data-stu-id="56184-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="56184-109">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="56184-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="56184-110">`Pauli`提供的運算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。</span><span class="sxs-lookup"><span data-stu-id="56184-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>