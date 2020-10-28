---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700618"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="7b06c-102">GreatestCommonDivisorI 函式</span><span class="sxs-lookup"><span data-stu-id="7b06c-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="7b06c-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7b06c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7b06c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b06c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b06c-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="7b06c-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="7b06c-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="7b06c-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="7b06c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7b06c-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7b06c-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b06c-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b06c-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="7b06c-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="7b06c-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b06c-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b06c-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="7b06c-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="7b06c-112">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b06c-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b06c-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="7b06c-113">Greatest common divisor of $a$ and $b$</span></span>