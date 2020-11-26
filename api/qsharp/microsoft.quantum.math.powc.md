---
uid: Microsoft.Quantum.Math.PowC
title: PowC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowC
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 57a0f4c8176a7f87835c7d096136e288c4875eea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194707"
---
# <a name="powc-function"></a><span data-ttu-id="b9a48-102">PowC 函式</span><span class="sxs-lookup"><span data-stu-id="b9a48-102">PowC function</span></span>

<span data-ttu-id="b9a48-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b9a48-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b9a48-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9a48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9a48-105">傳回指定乘冪的數位。</span><span class="sxs-lookup"><span data-stu-id="b9a48-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowC (a : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="b9a48-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b9a48-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="b9a48-107">a： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b9a48-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b9a48-108">要引發 $a $ 的數位。</span><span class="sxs-lookup"><span data-stu-id="b9a48-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complex"></a><span data-ttu-id="b9a48-109">強大功能： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b9a48-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b9a48-110">應該引發 $a $ 的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="b9a48-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complex"></a><span data-ttu-id="b9a48-111">輸出： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b9a48-111">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b9a48-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="b9a48-112">The power $a^b$</span></span>