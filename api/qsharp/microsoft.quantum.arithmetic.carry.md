---
uid: Microsoft.Quantum.Arithmetic.Carry
title: 執行操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843361"
---
# <a name="carry-operation"></a><span data-ttu-id="27f51-102">執行操作</span><span class="sxs-lookup"><span data-stu-id="27f51-102">Carry operation</span></span>

<span data-ttu-id="27f51-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27f51-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27f51-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27f51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27f51-105">會執行可還原的執行閘道。</span><span class="sxs-lookup"><span data-stu-id="27f51-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="27f51-106">給定量子位中編碼的執行位 `carryIn` 和在和中編碼的兩個被加數位 `summand1` `summand2` ，會計算中的位 xor `carryIn` ， `summand1` 而 `summand2` 在量子位中則 `summand2` 會進行 xor 至量子位 `carryOut` 。</span><span class="sxs-lookup"><span data-stu-id="27f51-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27f51-107">輸入</span><span class="sxs-lookup"><span data-stu-id="27f51-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="27f51-108">carryIn： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27f51-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27f51-109">執行量子位。</span><span class="sxs-lookup"><span data-stu-id="27f51-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="27f51-110">summand1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27f51-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27f51-111">第一個被加數量子位。</span><span class="sxs-lookup"><span data-stu-id="27f51-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="27f51-112">summand2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27f51-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27f51-113">第二個被加數量子位，會取代為和總和的低位 `summand1` `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="27f51-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="27f51-114">carryOut： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27f51-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27f51-115">執行量子位，將會以較高的總和位進行 xor。</span><span class="sxs-lookup"><span data-stu-id="27f51-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27f51-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27f51-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

