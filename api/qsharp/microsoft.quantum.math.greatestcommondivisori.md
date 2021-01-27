---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 9f76d5ac47faed9a353db4172cc9037411ab1198
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847306"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="a91af-102">GreatestCommonDivisorI 函式</span><span class="sxs-lookup"><span data-stu-id="a91af-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="a91af-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a91af-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a91af-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a91af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a91af-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="a91af-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="a91af-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="a91af-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a91af-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a91af-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a91af-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a91af-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a91af-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="a91af-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="a91af-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a91af-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a91af-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="a91af-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="a91af-112">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a91af-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a91af-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="a91af-113">Greatest common divisor of $a$ and $b$</span></span>