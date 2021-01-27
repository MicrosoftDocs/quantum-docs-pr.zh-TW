---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843214"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="6afb5-102">EvaluatePolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="6afb5-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="6afb5-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6afb5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6afb5-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="6afb5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="6afb5-105">在固定點標記法中評估多項式。</span><span class="sxs-lookup"><span data-stu-id="6afb5-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6afb5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6afb5-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="6afb5-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6afb5-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6afb5-108">多項式的係數做為雙精度浮點數陣列，也就是多項式 $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $ 的陣列 $ [a_0，a_1，...，a_d] $。</span><span class="sxs-lookup"><span data-stu-id="6afb5-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="6afb5-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6afb5-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6afb5-110">輸入要評估多項式的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="6afb5-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="6afb5-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6afb5-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6afb5-112">輸出將保留 $P (x) $ 的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="6afb5-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="6afb5-113">必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="6afb5-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6afb5-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6afb5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

