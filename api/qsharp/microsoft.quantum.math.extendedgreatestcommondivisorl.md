---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700635"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="0751a-102">ExtendedGreatestCommonDivisorL 函式</span><span class="sxs-lookup"><span data-stu-id="0751a-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="0751a-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0751a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0751a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0751a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0751a-105">計算元組 $ (u，v) $，以 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 和 $a $ $b $ 最大公因數。</span><span class="sxs-lookup"><span data-stu-id="0751a-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="0751a-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="0751a-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="0751a-107">輸入</span><span class="sxs-lookup"><span data-stu-id="0751a-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0751a-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0751a-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0751a-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="0751a-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="0751a-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0751a-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0751a-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="0751a-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="0751a-112">輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="0751a-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="0751a-113">元組 $ (u、v) $ 和屬性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。</span><span class="sxs-lookup"><span data-stu-id="0751a-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="0751a-114">參考</span><span class="sxs-lookup"><span data-stu-id="0751a-114">References</span></span>

- <span data-ttu-id="0751a-115">這項實行是根據 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="0751a-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>