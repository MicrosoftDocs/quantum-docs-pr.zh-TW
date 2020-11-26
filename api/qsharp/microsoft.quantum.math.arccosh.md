---
uid: Microsoft.Quantum.Math.ArcCosh
title: ArcCosh 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArcCosh
qsharp.summary: Computes the inverse hyperbolic cosine of a number.
ms.openlocfilehash: a919cd200b378e22aaef609e3c89ba39f3338042
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211214"
---
# <a name="arccosh-function"></a><span data-ttu-id="2e905-102">ArcCosh 函式</span><span class="sxs-lookup"><span data-stu-id="2e905-102">ArcCosh function</span></span>

<span data-ttu-id="2e905-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2e905-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2e905-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e905-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e905-105">計算數位的反雙曲余弦。</span><span class="sxs-lookup"><span data-stu-id="2e905-105">Computes the inverse hyperbolic cosine of a number.</span></span>

```qsharp
function ArcCosh (x : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2e905-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2e905-106">Input</span></span>

### <a name="x--double"></a><span data-ttu-id="2e905-107">x： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e905-107">x : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e905-108">$X \geq $1 的實數。</span><span class="sxs-lookup"><span data-stu-id="2e905-108">A real number $x\geq 1$.</span></span>



## <a name="output--double"></a><span data-ttu-id="2e905-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e905-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e905-110">實數 $y $，$x = \cosh (y) $。</span><span class="sxs-lookup"><span data-stu-id="2e905-110">A real number $y$ such that $x = \cosh(y)$.</span></span>