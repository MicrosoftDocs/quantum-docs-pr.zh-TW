---
uid: Microsoft.Quantum.Math.PowL
title: PowL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: b3207d1854f6b69cdb5b68d354000a0b6746c0c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228316"
---
# <a name="powl-function"></a><span data-ttu-id="5dd72-102">PowL 函式</span><span class="sxs-lookup"><span data-stu-id="5dd72-102">PowL function</span></span>

<span data-ttu-id="5dd72-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5dd72-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5dd72-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dd72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dd72-105">傳回指定乘冪的數位。</span><span class="sxs-lookup"><span data-stu-id="5dd72-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="5dd72-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5dd72-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5dd72-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5dd72-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5dd72-108">要引發 $a $ 的數位。</span><span class="sxs-lookup"><span data-stu-id="5dd72-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="5dd72-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dd72-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dd72-110">應該引發 $a $ 的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="5dd72-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5dd72-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5dd72-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5dd72-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="5dd72-112">The power $a^b$</span></span>