---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195499"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="14232-102">GreatestCommonDivisorL 函式</span><span class="sxs-lookup"><span data-stu-id="14232-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="14232-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="14232-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="14232-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14232-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14232-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="14232-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="14232-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="14232-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="14232-107">輸入</span><span class="sxs-lookup"><span data-stu-id="14232-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="14232-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="14232-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="14232-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="14232-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="14232-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="14232-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="14232-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="14232-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="14232-112">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="14232-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="14232-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="14232-113">Greatest common divisor of $a$ and $b$</span></span>