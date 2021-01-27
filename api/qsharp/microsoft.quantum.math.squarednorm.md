---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848208"
---
# <a name="squarednorm-function"></a><span data-ttu-id="73957-102">SquaredNorm 函式</span><span class="sxs-lookup"><span data-stu-id="73957-102">SquaredNorm function</span></span>

<span data-ttu-id="73957-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="73957-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="73957-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73957-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73957-105">傳回向量的平方二標準。</span><span class="sxs-lookup"><span data-stu-id="73957-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="73957-106">描述</span><span class="sxs-lookup"><span data-stu-id="73957-106">Description</span></span>

<span data-ttu-id="73957-107">傳回向量的平方二標準;亦即，假設輸入 $ \vec{x} $，則會傳回 $ \ sum_i x_i ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="73957-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="73957-108">輸入</span><span class="sxs-lookup"><span data-stu-id="73957-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="73957-109">陣列： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="73957-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="73957-110">要傳回其平方2標準的向量。</span><span class="sxs-lookup"><span data-stu-id="73957-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="73957-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73957-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73957-112">的平方雙標準 `array` 。</span><span class="sxs-lookup"><span data-stu-id="73957-112">The squared 2-norm of `array`.</span></span>