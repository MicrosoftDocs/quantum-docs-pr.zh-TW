---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847660"
---
# <a name="pnorm-function"></a><span data-ttu-id="38680-102">PNorm 函式</span><span class="sxs-lookup"><span data-stu-id="38680-102">PNorm function</span></span>

<span data-ttu-id="38680-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="38680-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="38680-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38680-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38680-105">傳回 `L(p)` 向量的標準 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="38680-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="38680-106">亦即，假設陣列 $x $ 的型 `Double[]` 別，這會傳回 $p $-標準 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。</span><span class="sxs-lookup"><span data-stu-id="38680-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="38680-107">輸入</span><span class="sxs-lookup"><span data-stu-id="38680-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="38680-108">p： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38680-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38680-109">$P $-標準中的指數 $p $。</span><span class="sxs-lookup"><span data-stu-id="38680-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="38680-110">陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="38680-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="38680-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38680-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38680-112">$P $-標準 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="38680-112">The $p$-norm $\|x\|_p$.</span></span>