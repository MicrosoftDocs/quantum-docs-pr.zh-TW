---
uid: Microsoft.Quantum.Math.ArcCosh
title: ArcCosh 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArcCosh
qsharp.summary: Computes the inverse hyperbolic cosine of a number.
ms.openlocfilehash: 5598e45f7cc34cdc686b26655c267a06b8476db0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848955"
---
# <a name="arccosh-function"></a><span data-ttu-id="25cc6-102">ArcCosh 函式</span><span class="sxs-lookup"><span data-stu-id="25cc6-102">ArcCosh function</span></span>

<span data-ttu-id="25cc6-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="25cc6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="25cc6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25cc6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25cc6-105">計算數位的反雙曲余弦。</span><span class="sxs-lookup"><span data-stu-id="25cc6-105">Computes the inverse hyperbolic cosine of a number.</span></span>

```qsharp
function ArcCosh (x : Double) : Double
```


## <a name="input"></a><span data-ttu-id="25cc6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="25cc6-106">Input</span></span>

### <a name="x--double"></a><span data-ttu-id="25cc6-107">x： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25cc6-107">x : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25cc6-108">$X \geq $1 的實數。</span><span class="sxs-lookup"><span data-stu-id="25cc6-108">A real number $x\geq 1$.</span></span>



## <a name="output--double"></a><span data-ttu-id="25cc6-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25cc6-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25cc6-110">實數 $y $，$x = \cosh (y) $。</span><span class="sxs-lookup"><span data-stu-id="25cc6-110">A real number $y$ such that $x = \cosh(y)$.</span></span>