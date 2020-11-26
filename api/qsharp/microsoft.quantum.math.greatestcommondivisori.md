---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 2b6ba8a6d5ac78b69e6ee20160f3a3b1df61a879
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228469"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="f39f7-102">GreatestCommonDivisorI 函式</span><span class="sxs-lookup"><span data-stu-id="f39f7-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="f39f7-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f39f7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f39f7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f39f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f39f7-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="f39f7-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="f39f7-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="f39f7-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f39f7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f39f7-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f39f7-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f39f7-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f39f7-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="f39f7-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="f39f7-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f39f7-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f39f7-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="f39f7-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="f39f7-112">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f39f7-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f39f7-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="f39f7-113">Greatest common divisor of $a$ and $b$</span></span>