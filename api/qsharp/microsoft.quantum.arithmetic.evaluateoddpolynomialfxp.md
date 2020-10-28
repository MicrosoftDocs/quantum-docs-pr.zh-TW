---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699891"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="083ee-102">EvaluateOddPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="083ee-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="083ee-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="083ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="083ee-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="083ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="083ee-105">評估固定點標記法中的奇多項式。</span><span class="sxs-lookup"><span data-stu-id="083ee-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="083ee-106">輸入</span><span class="sxs-lookup"><span data-stu-id="083ee-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="083ee-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="083ee-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="083ee-108">奇多項式的係數，例如 double 陣列，也就是陣列 $ [a_0，a_1，...，a_k] $ 代表奇數多項式 $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $。</span><span class="sxs-lookup"><span data-stu-id="083ee-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="083ee-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="083ee-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="083ee-110">輸入要評估多項式的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="083ee-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="083ee-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="083ee-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="083ee-112">輸出將保留 P (x) 的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="083ee-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="083ee-113">必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="083ee-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="083ee-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="083ee-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

