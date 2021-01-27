---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856367"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="b7cd1-102">GreatestCommonDivisorL 函式</span><span class="sxs-lookup"><span data-stu-id="b7cd1-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="b7cd1-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b7cd1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b7cd1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7cd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7cd1-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="b7cd1-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="b7cd1-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="b7cd1-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b7cd1-107">輸入</span><span class="sxs-lookup"><span data-stu-id="b7cd1-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b7cd1-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b7cd1-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b7cd1-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="b7cd1-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b7cd1-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b7cd1-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b7cd1-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="b7cd1-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b7cd1-112">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b7cd1-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b7cd1-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="b7cd1-113">Greatest common divisor of $a$ and $b$</span></span>