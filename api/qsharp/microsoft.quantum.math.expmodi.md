---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700535"
---
# <a name="expmodi-function"></a><span data-ttu-id="2f20f-102">ExpModI 函式</span><span class="sxs-lookup"><span data-stu-id="2f20f-102">ExpModI function</span></span>

<span data-ttu-id="2f20f-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2f20f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2f20f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f20f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f20f-105">針對給定的模數，傳回引發至給定乘冪的整數。</span><span class="sxs-lookup"><span data-stu-id="2f20f-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="2f20f-106">描述</span><span class="sxs-lookup"><span data-stu-id="2f20f-106">Description</span></span>

<span data-ttu-id="2f20f-107">讓我們以 $x $、乘 $p $ 和模數 $N $ 來表示 expBase。</span><span class="sxs-lookup"><span data-stu-id="2f20f-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="2f20f-108">函數會傳回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="2f20f-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="2f20f-109">我們假設 $N $、$x $ 為正面且電源為非負數。</span><span class="sxs-lookup"><span data-stu-id="2f20f-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="2f20f-110">輸入</span><span class="sxs-lookup"><span data-stu-id="2f20f-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="2f20f-111">expBase： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f20f-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="2f20f-112">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f20f-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="2f20f-113">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f20f-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="2f20f-114">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f20f-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="2f20f-115">備註</span><span class="sxs-lookup"><span data-stu-id="2f20f-115">Remarks</span></span>

<span data-ttu-id="2f20f-116">花費的時間與中的位數成正比 `power` ，而不是本身的位數 `power` 。</span><span class="sxs-lookup"><span data-stu-id="2f20f-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>