---
uid: Microsoft.Quantum.Math.Lg
title: Lg 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Lg
qsharp.summary: Computes the base-2 logarithm of a number.
ms.openlocfilehash: eef4d5b23298250ad6c0553788fca4c88d7836e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195285"
---
# <a name="lg-function"></a><span data-ttu-id="4d284-102">Lg 函式</span><span class="sxs-lookup"><span data-stu-id="4d284-102">Lg function</span></span>

<span data-ttu-id="4d284-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4d284-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4d284-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d284-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d284-105">計算數位的以2為底數的對數。</span><span class="sxs-lookup"><span data-stu-id="4d284-105">Computes the base-2 logarithm of a number.</span></span>

```qsharp
function Lg (input : Double) : Double
```


## <a name="input"></a><span data-ttu-id="4d284-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4d284-106">Input</span></span>

### <a name="input--double"></a><span data-ttu-id="4d284-107">輸入： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d284-107">input : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d284-108">$X $ 的實數。</span><span class="sxs-lookup"><span data-stu-id="4d284-108">A real number $x$.</span></span>



## <a name="output--double"></a><span data-ttu-id="4d284-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d284-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d284-110">以2為底數的對數 $y = \ log_2 (x) $，如此 $x = 2 ^ y $。</span><span class="sxs-lookup"><span data-stu-id="4d284-110">The base-2 logarithm $y = \log_2(x)$ such that $x = 2^y$.</span></span>