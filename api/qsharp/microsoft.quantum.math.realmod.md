---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228248"
---
# <a name="realmod-function"></a><span data-ttu-id="2a385-102">RealMod 函式</span><span class="sxs-lookup"><span data-stu-id="2a385-102">RealMod function</span></span>

<span data-ttu-id="2a385-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2a385-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2a385-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a385-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a385-105">計算兩個實數之間的模數。</span><span class="sxs-lookup"><span data-stu-id="2a385-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2a385-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2a385-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="2a385-107">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a385-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a385-108">$X $ 取得模數的實數。</span><span class="sxs-lookup"><span data-stu-id="2a385-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="2a385-109">模數： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a385-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a385-110">要採用 $x $ 的模數的實際數位。</span><span class="sxs-lookup"><span data-stu-id="2a385-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="2a385-111">minValue： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a385-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a385-112">此函數所傳回的最小值。</span><span class="sxs-lookup"><span data-stu-id="2a385-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="2a385-113">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a385-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="2a385-114">備註</span><span class="sxs-lookup"><span data-stu-id="2a385-114">Remarks</span></span>

<span data-ttu-id="2a385-115">此函式會藉由包裝單元圓圈相關的實數來計算實際模數，然後尋找對應于輸入的單位圓形上的角度。</span><span class="sxs-lookup"><span data-stu-id="2a385-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="2a385-116">`minValue`然後，輸入會有效地指定要將單元圓形剪下的位置。</span><span class="sxs-lookup"><span data-stu-id="2a385-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>