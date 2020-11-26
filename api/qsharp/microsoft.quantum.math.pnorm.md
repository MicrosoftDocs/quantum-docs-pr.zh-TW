---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194724"
---
# <a name="pnorm-function"></a><span data-ttu-id="e187b-102">PNorm 函式</span><span class="sxs-lookup"><span data-stu-id="e187b-102">PNorm function</span></span>

<span data-ttu-id="e187b-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e187b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e187b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e187b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e187b-105">傳回 `L(p)` 向量的標準 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="e187b-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="e187b-106">亦即，假設陣列 $x $ 的型 `Double[]` 別，這會傳回 $p $-標準 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。</span><span class="sxs-lookup"><span data-stu-id="e187b-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="e187b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e187b-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="e187b-108">p： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e187b-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e187b-109">$P $-標準中的指數 $p $。</span><span class="sxs-lookup"><span data-stu-id="e187b-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="e187b-110">陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e187b-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="e187b-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e187b-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e187b-112">$P $-標準 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="e187b-112">The $p$-norm $\|x\|_p$.</span></span>