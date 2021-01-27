---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e86237f39e696485a3496f1c6dd571cd516214ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857544"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="bb343-102">ExtendedGreatestCommonDivisorI 函式</span><span class="sxs-lookup"><span data-stu-id="bb343-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="bb343-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bb343-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bb343-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb343-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb343-105">計算元組 $ (u，v) $，以 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 和 $a $ $b $ 最大公因數。</span><span class="sxs-lookup"><span data-stu-id="bb343-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="bb343-106">GCD 一律為正數。</span><span class="sxs-lookup"><span data-stu-id="bb343-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="bb343-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bb343-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="bb343-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb343-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb343-109">要計算的第一個擴充最大公除數</span><span class="sxs-lookup"><span data-stu-id="bb343-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="bb343-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb343-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb343-111">計算最大最大公除數的第二個數字</span><span class="sxs-lookup"><span data-stu-id="bb343-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="bb343-112">輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="bb343-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="bb343-113">元組 $ (u、v) $ 和屬性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。</span><span class="sxs-lookup"><span data-stu-id="bb343-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="bb343-114">參考資料</span><span class="sxs-lookup"><span data-stu-id="bb343-114">References</span></span>

- <span data-ttu-id="bb343-115">這項實行是根據 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="bb343-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>