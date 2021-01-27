---
title: 使用 Microsoft Q# 數值程式庫
description: 深入瞭解 Microsoft 量子數值程式庫中可用的類型和操作。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: 92efd3b8677d2f27bc59f986ce6c9e915cd23652
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856435"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="8631e-103">使用數值程式庫</span><span class="sxs-lookup"><span data-stu-id="8631e-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="8631e-104">概觀</span><span class="sxs-lookup"><span data-stu-id="8631e-104">Overview</span></span>

<span data-ttu-id="8631e-105">數值程式庫包含三個元件</span><span class="sxs-lookup"><span data-stu-id="8631e-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="8631e-106">整數 adder 和比較子的 **基本整數算術**</span><span class="sxs-lookup"><span data-stu-id="8631e-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="8631e-107">建置於基本功能之上的 **高階整數功能**;它包含乘法、除法、反轉等等。 用於帶正負號和不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="8631e-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="8631e-108">具有固定點初始化、加法、乘法、倒數、多項式評估和測量的 **定點算術功能**。</span><span class="sxs-lookup"><span data-stu-id="8631e-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="8631e-109">所有這些元件都可以使用單一語句來存取 `open` ：</span><span class="sxs-lookup"><span data-stu-id="8631e-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="8631e-110">類型</span><span class="sxs-lookup"><span data-stu-id="8631e-110">Types</span></span>

<span data-ttu-id="8631e-111">數值程式庫支援下列類型</span><span class="sxs-lookup"><span data-stu-id="8631e-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="8631e-112">**`LittleEndian`**：表示整數的量子位陣列 `qArr : Qubit[]` ，其中表示 `qArr[0]` 最小的位。</span><span class="sxs-lookup"><span data-stu-id="8631e-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="8631e-113">**`SignedLittleEndian`**：與 `LittleEndian` 不同之處在于，它代表以二補數儲存的帶正負號整數。</span><span class="sxs-lookup"><span data-stu-id="8631e-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="8631e-114">**`FixedPoint`**：代表量子位陣列 `qArr2 : Qubit[]` 和二進位點位置所組成的實數 `pos` ，其會計算二進位點左邊的二進位位數數目。</span><span class="sxs-lookup"><span data-stu-id="8631e-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="8631e-115">`qArr2` 的儲存方式與相同 `SignedLittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="8631e-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="8631e-116">Operations</span><span class="sxs-lookup"><span data-stu-id="8631e-116">Operations</span></span>

<span data-ttu-id="8631e-117">上述三種類型的每一個都有提供各種不同的作業：</span><span class="sxs-lookup"><span data-stu-id="8631e-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="8631e-118">加法</span><span class="sxs-lookup"><span data-stu-id="8631e-118">Addition</span></span>
    - <span data-ttu-id="8631e-119">比較</span><span class="sxs-lookup"><span data-stu-id="8631e-119">Comparison</span></span>
    - <span data-ttu-id="8631e-120">乘法</span><span class="sxs-lookup"><span data-stu-id="8631e-120">Multiplication</span></span>
    - <span data-ttu-id="8631e-121">平方</span><span class="sxs-lookup"><span data-stu-id="8631e-121">Squaring</span></span>
    - <span data-ttu-id="8631e-122">具有餘數的除法 () </span><span class="sxs-lookup"><span data-stu-id="8631e-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="8631e-123">加法</span><span class="sxs-lookup"><span data-stu-id="8631e-123">Addition</span></span>
    - <span data-ttu-id="8631e-124">比較</span><span class="sxs-lookup"><span data-stu-id="8631e-124">Comparison</span></span>
    - <span data-ttu-id="8631e-125">反轉模數2補數</span><span class="sxs-lookup"><span data-stu-id="8631e-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="8631e-126">乘法</span><span class="sxs-lookup"><span data-stu-id="8631e-126">Multiplication</span></span>
    - <span data-ttu-id="8631e-127">平方</span><span class="sxs-lookup"><span data-stu-id="8631e-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="8631e-128">針對傳統值進行準備/初始化</span><span class="sxs-lookup"><span data-stu-id="8631e-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="8631e-129">加法 (傳統常數或其他量子固定點) </span><span class="sxs-lookup"><span data-stu-id="8631e-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="8631e-130">比較</span><span class="sxs-lookup"><span data-stu-id="8631e-130">Comparison</span></span>
    - <span data-ttu-id="8631e-131">乘法</span><span class="sxs-lookup"><span data-stu-id="8631e-131">Multiplication</span></span>
    - <span data-ttu-id="8631e-132">平方</span><span class="sxs-lookup"><span data-stu-id="8631e-132">Squaring</span></span>
    - <span data-ttu-id="8631e-133">針對偶數和奇數函數特製化的多項式評估</span><span class="sxs-lookup"><span data-stu-id="8631e-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="8631e-134">反向 (1/x) </span><span class="sxs-lookup"><span data-stu-id="8631e-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="8631e-135"> (傳統雙精度) 的度量</span><span class="sxs-lookup"><span data-stu-id="8631e-135">Measurement (classical Double)</span></span>

<span data-ttu-id="8631e-136">如需這些作業的詳細資訊和詳細檔，請參閱連結 Q# 庫參考檔，網址 [docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="8631e-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="8631e-137">範例：整數加法</span><span class="sxs-lookup"><span data-stu-id="8631e-137">Sample: Integer addition</span></span>

<span data-ttu-id="8631e-138">作為基本範例，請考慮作業 $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是採用 n-量子位整數 $x $ 和 n 或 (n + 1) -量子位登錄 $y $ 做為輸入，後者對應至 sum $ (x + y) $。</span><span class="sxs-lookup"><span data-stu-id="8631e-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="8631e-139">請注意，如果 $y $ 儲存在 $n $ 位登錄中，則總和會計算模數 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="8631e-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="8631e-140">您可以使用量子開發工具組來套用此作業，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8631e-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="8631e-141">範例：評估平滑函數</span><span class="sxs-lookup"><span data-stu-id="8631e-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="8631e-142">若要在量子電腦上評估平滑的函式（例如 $ \sin (x) $，其中 $x $ 是量子 `FixedPoint` 數位），則量子開發工具組數值程式庫會提供作業 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP` 。</span><span class="sxs-lookup"><span data-stu-id="8631e-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="8631e-143">第一個是， `EvaluatePolynomialFxP` 可讓您評估 "$ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 的多項式，其中 $d $ 表示 *度數*。</span><span class="sxs-lookup"><span data-stu-id="8631e-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="8631e-144">若要這樣做，您只需要) 類型的多項式係數 `[a_0,..., a_d]` (`Double[]` 、輸入 `x : FixedPoint` 和輸出 `y : FixedPoint` (一開始零) ：</span><span class="sxs-lookup"><span data-stu-id="8631e-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8631e-145">結果（$P (x) = 1 + 2x $）將儲存在中 `yFxP` 。</span><span class="sxs-lookup"><span data-stu-id="8631e-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="8631e-146">第二個、 `EvaluateEvenPolynomialFxP` 和第三個 `EvaluateOddPolynomialFxP` 分別是偶數和奇數函數的特殊化。</span><span class="sxs-lookup"><span data-stu-id="8631e-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="8631e-147">也就是說，針對偶數/奇數函數 $f (x) $ 和 $ $ P_ {偶數} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d} $ $ $f (x) $ 相當適合 $P _ {偶數} (x) $ 或 $P _ {奇數} (x) ： = x\cdot P_ {偶數} (x) $。</span><span class="sxs-lookup"><span data-stu-id="8631e-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="8631e-148">在中 Q# ，這兩個案例可以依照下列方式處理：</span><span class="sxs-lookup"><span data-stu-id="8631e-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8631e-149">它會評估 $P _ {偶數} (x) = 1 + 2x ^ 2 $，以及</span><span class="sxs-lookup"><span data-stu-id="8631e-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8631e-150">它會評估 $P _ {奇數} (x) = x + 2x ^ 3 $。</span><span class="sxs-lookup"><span data-stu-id="8631e-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="8631e-151">其他範例</span><span class="sxs-lookup"><span data-stu-id="8631e-151">More samples</span></span>

<span data-ttu-id="8631e-152">您可以在 [主要範例儲存](https://github.com/Microsoft/Quantum)機制中找到更多範例。</span><span class="sxs-lookup"><span data-stu-id="8631e-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="8631e-153">若要開始使用，請複製存放庫，並開啟 `Numerics` 子資料夾：</span><span class="sxs-lookup"><span data-stu-id="8631e-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

<span data-ttu-id="8631e-154">然後，在 `cd` 其中一個範例資料夾中，並透過下列方式執行範例：</span><span class="sxs-lookup"><span data-stu-id="8631e-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
