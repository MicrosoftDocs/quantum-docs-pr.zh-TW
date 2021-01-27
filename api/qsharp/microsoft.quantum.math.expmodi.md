---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857042"
---
# <a name="expmodi-function"></a><span data-ttu-id="7e3f3-102">ExpModI 函式</span><span class="sxs-lookup"><span data-stu-id="7e3f3-102">ExpModI function</span></span>

<span data-ttu-id="7e3f3-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7e3f3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e3f3-105">針對給定的模數，傳回引發至給定乘冪的整數。</span><span class="sxs-lookup"><span data-stu-id="7e3f3-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="7e3f3-106">描述</span><span class="sxs-lookup"><span data-stu-id="7e3f3-106">Description</span></span>

<span data-ttu-id="7e3f3-107">讓我們以 $x $、乘 $p $ 和模數 $N $ 來表示 expBase。</span><span class="sxs-lookup"><span data-stu-id="7e3f3-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="7e3f3-108">函數會傳回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="7e3f3-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="7e3f3-109">我們假設 $N $、$x $ 為正面且電源為非負數。</span><span class="sxs-lookup"><span data-stu-id="7e3f3-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="7e3f3-110">輸入</span><span class="sxs-lookup"><span data-stu-id="7e3f3-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="7e3f3-111">expBase： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="7e3f3-112">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="7e3f3-113">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="7e3f3-114">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3f3-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="7e3f3-115">備註</span><span class="sxs-lookup"><span data-stu-id="7e3f3-115">Remarks</span></span>

<span data-ttu-id="7e3f3-116">花費的時間與中的位數成正比 `power` ，而不是本身的位數 `power` 。</span><span class="sxs-lookup"><span data-stu-id="7e3f3-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>