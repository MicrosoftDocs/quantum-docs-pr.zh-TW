---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1445f1c3d2a5852459a492fa5e6bfd2a685786d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857523"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="9afb7-102">ExtendedGreatestCommonDivisorL 函式</span><span class="sxs-lookup"><span data-stu-id="9afb7-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="9afb7-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9afb7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9afb7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9afb7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9afb7-105">計算元組 $ (u，v) $，以 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 和 $a $ $b $ 最大公因數。</span><span class="sxs-lookup"><span data-stu-id="9afb7-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="9afb7-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="9afb7-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="9afb7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="9afb7-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9afb7-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9afb7-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9afb7-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="9afb7-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9afb7-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9afb7-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9afb7-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="9afb7-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="9afb7-112">輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="9afb7-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="9afb7-113">元組 $ (u、v) $ 和屬性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。</span><span class="sxs-lookup"><span data-stu-id="9afb7-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="9afb7-114">參考資料</span><span class="sxs-lookup"><span data-stu-id="9afb7-114">References</span></span>

- <span data-ttu-id="9afb7-115">這項實行是根據 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="9afb7-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>