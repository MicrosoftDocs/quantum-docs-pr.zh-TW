---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700615"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="223c9-102">GreatestCommonDivisorL 函式</span><span class="sxs-lookup"><span data-stu-id="223c9-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="223c9-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="223c9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="223c9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="223c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="223c9-105">計算 $a $ 和 $b $ 的最大公因數。</span><span class="sxs-lookup"><span data-stu-id="223c9-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="223c9-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="223c9-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="223c9-107">輸入</span><span class="sxs-lookup"><span data-stu-id="223c9-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="223c9-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="223c9-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="223c9-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="223c9-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="223c9-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="223c9-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="223c9-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="223c9-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="223c9-112">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="223c9-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="223c9-113">$a $ 和 $b $ 的最大公除數</span><span class="sxs-lookup"><span data-stu-id="223c9-113">Greatest common divisor of $a$ and $b$</span></span>