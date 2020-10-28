---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699894"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="b8e6c-102">EvaluateEvenPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="b8e6c-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="b8e6c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b8e6c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b8e6c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8e6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8e6c-105">在固定點標記法中評估偶數多項式。</span><span class="sxs-lookup"><span data-stu-id="b8e6c-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="b8e6c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b8e6c-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="b8e6c-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b8e6c-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b8e6c-108">偶數多項式的係數，例如 double 陣列，也就是陣列 $ [a_0，a_1，...，a_k] $ 表示偶數多項式 $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $。</span><span class="sxs-lookup"><span data-stu-id="b8e6c-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="b8e6c-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b8e6c-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b8e6c-110">輸入要評估多項式的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="b8e6c-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="b8e6c-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b8e6c-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b8e6c-112">輸出將保留 $P (x) $ 的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="b8e6c-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="b8e6c-113">必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="b8e6c-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8e6c-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8e6c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

