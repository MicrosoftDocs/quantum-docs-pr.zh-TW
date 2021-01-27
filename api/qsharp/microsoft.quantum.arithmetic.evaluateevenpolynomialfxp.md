---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843239"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="a21d5-102">EvaluateEvenPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="a21d5-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="a21d5-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a21d5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a21d5-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a21d5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a21d5-105">在固定點標記法中評估偶數多項式。</span><span class="sxs-lookup"><span data-stu-id="a21d5-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a21d5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a21d5-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a21d5-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a21d5-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a21d5-108">偶數多項式的係數，例如 double 陣列，也就是陣列 $ [a_0，a_1，...，a_k] $ 表示偶數多項式 $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $。</span><span class="sxs-lookup"><span data-stu-id="a21d5-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="a21d5-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a21d5-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a21d5-110">輸入要評估多項式的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="a21d5-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a21d5-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a21d5-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a21d5-112">輸出將保留 $P (x) $ 的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="a21d5-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="a21d5-113">必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="a21d5-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a21d5-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a21d5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

