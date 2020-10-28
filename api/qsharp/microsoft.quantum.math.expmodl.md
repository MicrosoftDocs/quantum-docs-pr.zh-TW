---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700639"
---
# <a name="expmodl-function"></a><span data-ttu-id="d44a8-102">ExpModL 函式</span><span class="sxs-lookup"><span data-stu-id="d44a8-102">ExpModL function</span></span>

<span data-ttu-id="d44a8-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d44a8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d44a8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d44a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d44a8-105">針對給定的模數，傳回引發至給定乘冪的整數。</span><span class="sxs-lookup"><span data-stu-id="d44a8-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="d44a8-106">描述</span><span class="sxs-lookup"><span data-stu-id="d44a8-106">Description</span></span>

<span data-ttu-id="d44a8-107">讓我們以 $x $、乘 $p $ 和模數 $N $ 來表示 expBase。</span><span class="sxs-lookup"><span data-stu-id="d44a8-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="d44a8-108">函數會傳回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="d44a8-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="d44a8-109">我們假設 $N $、$x $ 為正面且電源為非負數。</span><span class="sxs-lookup"><span data-stu-id="d44a8-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="d44a8-110">輸入</span><span class="sxs-lookup"><span data-stu-id="d44a8-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="d44a8-111">expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44a8-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="d44a8-112">power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44a8-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="d44a8-113">模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44a8-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="d44a8-114">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44a8-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="d44a8-115">備註</span><span class="sxs-lookup"><span data-stu-id="d44a8-115">Remarks</span></span>

<span data-ttu-id="d44a8-116">花費的時間與中的位數成正比 `power` ，而不是本身的位數 `power` 。</span><span class="sxs-lookup"><span data-stu-id="d44a8-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>