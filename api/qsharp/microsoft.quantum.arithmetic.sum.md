---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 總和運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699527"
---
# <a name="sum-operation"></a><span data-ttu-id="9bafb-102">總和運算</span><span class="sxs-lookup"><span data-stu-id="9bafb-102">Sum operation</span></span>

<span data-ttu-id="9bafb-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9bafb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9bafb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9bafb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9bafb-105">實行可還原的總和閘道。</span><span class="sxs-lookup"><span data-stu-id="9bafb-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="9bafb-106">給定量子位中編碼的執行位 `carryIn` 和在和中編碼的兩個被加數位時 `summand1` ，會 `summand2` `carryIn` `summand1` `summand2` 在量子位中計算的位 xor 和 `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="9bafb-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9bafb-107">輸入</span><span class="sxs-lookup"><span data-stu-id="9bafb-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="9bafb-108">carryIn： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9bafb-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9bafb-109">執行量子位。</span><span class="sxs-lookup"><span data-stu-id="9bafb-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="9bafb-110">summand1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9bafb-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9bafb-111">第一個被加數量子位。</span><span class="sxs-lookup"><span data-stu-id="9bafb-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="9bafb-112">summand2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9bafb-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9bafb-113">第二個被加數量子位，會取代為和總和的低位 `summand1` `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="9bafb-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9bafb-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bafb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9bafb-115">備註</span><span class="sxs-lookup"><span data-stu-id="9bafb-115">Remarks</span></span>

<span data-ttu-id="9bafb-116">相對於作業 `Carry` ，這不會計算執行時位。</span><span class="sxs-lookup"><span data-stu-id="9bafb-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>