---
uid: Microsoft.Quantum.Math.Lg
title: Lg 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Lg
qsharp.summary: Computes the base-2 logarithm of a number.
ms.openlocfilehash: da6548691437ffd9470bc93e6a69c8d38854c984
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851320"
---
# <a name="lg-function"></a><span data-ttu-id="577f1-102">Lg 函式</span><span class="sxs-lookup"><span data-stu-id="577f1-102">Lg function</span></span>

<span data-ttu-id="577f1-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="577f1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="577f1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="577f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="577f1-105">計算數位的以2為底數的對數。</span><span class="sxs-lookup"><span data-stu-id="577f1-105">Computes the base-2 logarithm of a number.</span></span>

```qsharp
function Lg (input : Double) : Double
```


## <a name="input"></a><span data-ttu-id="577f1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="577f1-106">Input</span></span>

### <a name="input--double"></a><span data-ttu-id="577f1-107">輸入： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="577f1-107">input : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="577f1-108">$X $ 的實數。</span><span class="sxs-lookup"><span data-stu-id="577f1-108">A real number $x$.</span></span>



## <a name="output--double"></a><span data-ttu-id="577f1-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="577f1-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="577f1-110">以2為底數的對數 $y = \ log_2 (x) $，如此 $x = 2 ^ y $。</span><span class="sxs-lookup"><span data-stu-id="577f1-110">The base-2 logarithm $y = \log_2(x)$ such that $x = 2^y$.</span></span>