---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227517"
---
# <a name="pnormalized-function"></a><span data-ttu-id="ded02-102">PNormalized 函式</span><span class="sxs-lookup"><span data-stu-id="ded02-102">PNormalized function</span></span>

<span data-ttu-id="ded02-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ded02-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ded02-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ded02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ded02-105">標準化 `Double` 標準中的向量 `L(p)` 。</span><span class="sxs-lookup"><span data-stu-id="ded02-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="ded02-106">亦即，假設陣列 $x $ 的型別 `Double[]` ，則會傳回陣列，其中所有專案都除以 $p $-標準 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="ded02-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="ded02-107">輸入</span><span class="sxs-lookup"><span data-stu-id="ded02-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="ded02-108">p： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ded02-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ded02-109">$P $-標準中的指數 $p $。</span><span class="sxs-lookup"><span data-stu-id="ded02-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="ded02-110">陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ded02-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="ded02-111">輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ded02-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ded02-112">陣列 $x $ $p $-標準 $ \| x _p $ 的正規化 \| 。</span><span class="sxs-lookup"><span data-stu-id="ded02-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="ded02-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ded02-113">See Also</span></span>

- [<span data-ttu-id="ded02-114">PNorm。</span><span class="sxs-lookup"><span data-stu-id="ded02-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)