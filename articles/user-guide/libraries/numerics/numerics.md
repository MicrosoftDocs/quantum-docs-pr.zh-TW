---
title: '使用 Microsoft Q # 數值程式庫'
description: 瞭解 Microsoft 量子數值程式庫中可用的類型和作業。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274700"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="fdfd1-103">使用數值程式庫</span><span class="sxs-lookup"><span data-stu-id="fdfd1-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="fdfd1-104">概觀</span><span class="sxs-lookup"><span data-stu-id="fdfd1-104">Overview</span></span>

<span data-ttu-id="fdfd1-105">數值程式庫是由三個元件所組成</span><span class="sxs-lookup"><span data-stu-id="fdfd1-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="fdfd1-106">整數 adders 和比較子的**基本整數算術**</span><span class="sxs-lookup"><span data-stu-id="fdfd1-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="fdfd1-107">**高階整數功能**是建置於基本功能之上;其中包括乘法、除法、反轉等等。 適用于帶正負號和不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="fdfd1-108">具有固定點初始化、加法、乘法、倒數、多項式評估和測量的**定點算術功能**。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="fdfd1-109">所有這些元件都可以使用單一語句來存取 `open` ：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="fdfd1-110">類型</span><span class="sxs-lookup"><span data-stu-id="fdfd1-110">Types</span></span>

<span data-ttu-id="fdfd1-111">數值程式庫支援下列類型</span><span class="sxs-lookup"><span data-stu-id="fdfd1-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="fdfd1-112">**`LittleEndian`**：代表整數的 qubit 陣列 `qArr : Qubit[]` ，其中表示 `qArr[0]` 最不重要的位。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="fdfd1-113">**`SignedLittleEndian`**：與相同 `LittleEndian` ，不同之處在于它代表儲存在兩個補數中的帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="fdfd1-114">**`FixedPoint`**：代表由 qubit 陣列 `qArr2 : Qubit[]` 和二進位點位置組成的實數 `pos` ，其會計算二進位點左邊的二進位數。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="fdfd1-115">`qArr2`的儲存方式與相同 `SignedLittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="fdfd1-116">作業</span><span class="sxs-lookup"><span data-stu-id="fdfd1-116">Operations</span></span>

<span data-ttu-id="fdfd1-117">針對上述三種類型的每一種，可以使用各種不同的作業：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="fdfd1-118">加法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-118">Addition</span></span>
    - <span data-ttu-id="fdfd1-119">比較</span><span class="sxs-lookup"><span data-stu-id="fdfd1-119">Comparison</span></span>
    - <span data-ttu-id="fdfd1-120">乘法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-120">Multiplication</span></span>
    - <span data-ttu-id="fdfd1-121">求</span><span class="sxs-lookup"><span data-stu-id="fdfd1-121">Squaring</span></span>
    - <span data-ttu-id="fdfd1-122">除法（含餘數）</span><span class="sxs-lookup"><span data-stu-id="fdfd1-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="fdfd1-123">加法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-123">Addition</span></span>
    - <span data-ttu-id="fdfd1-124">比較</span><span class="sxs-lookup"><span data-stu-id="fdfd1-124">Comparison</span></span>
    - <span data-ttu-id="fdfd1-125">反轉模數2補數</span><span class="sxs-lookup"><span data-stu-id="fdfd1-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="fdfd1-126">乘法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-126">Multiplication</span></span>
    - <span data-ttu-id="fdfd1-127">求</span><span class="sxs-lookup"><span data-stu-id="fdfd1-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="fdfd1-128">準備/初始化為傳統值</span><span class="sxs-lookup"><span data-stu-id="fdfd1-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="fdfd1-129">加法（傳統常數或其他配量固定點）</span><span class="sxs-lookup"><span data-stu-id="fdfd1-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="fdfd1-130">比較</span><span class="sxs-lookup"><span data-stu-id="fdfd1-130">Comparison</span></span>
    - <span data-ttu-id="fdfd1-131">乘法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-131">Multiplication</span></span>
    - <span data-ttu-id="fdfd1-132">求</span><span class="sxs-lookup"><span data-stu-id="fdfd1-132">Squaring</span></span>
    - <span data-ttu-id="fdfd1-133">對偶數和奇數函式的特製化進行多項式評估</span><span class="sxs-lookup"><span data-stu-id="fdfd1-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="fdfd1-134">倒數（1/x）</span><span class="sxs-lookup"><span data-stu-id="fdfd1-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="fdfd1-135">測量（傳統雙精度浮點數）</span><span class="sxs-lookup"><span data-stu-id="fdfd1-135">Measurement (classical Double)</span></span>

<span data-ttu-id="fdfd1-136">如需每一項作業的詳細資訊和詳細檔，請參閱 Q # 程式庫參考檔，網址為[docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="fdfd1-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="fdfd1-137">範例：整數加法</span><span class="sxs-lookup"><span data-stu-id="fdfd1-137">Sample: Integer addition</span></span>

<span data-ttu-id="fdfd1-138">作為基本範例，請考慮 operation $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是採用 n-qubit 整數的作業，$x $ 和 n 或（n + 1）-qubit 暫存器 $y $ 做為輸入，後者會對應到 sum $ （x + y） $。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="fdfd1-139">請注意，如果 $y $ 儲存在 $n $ bit 暫存器中，則總和為計算的模數 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="fdfd1-140">使用配量開發工具組時，可以套用此作業，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
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

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="fdfd1-141">範例：評估平滑功能</span><span class="sxs-lookup"><span data-stu-id="fdfd1-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="fdfd1-142">若要在量子電腦上評估如 $ \sin （x） $ 之類的平滑功能，其中 $x $ 是配 `FixedPoint` 量編號，則「量子開發工具組數值程式庫」會提供作業 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP` 。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="fdfd1-143">第一個是，可 `EvaluatePolynomialFxP` 讓評估格式為 $ $ P （x） = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 的多項式，其中 $d $ 代表該*程度*。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="fdfd1-144">若要這麼做，只需要多項式係數 `[a_0,..., a_d]` （類型為 `Double[]` ）、輸入 `x : FixedPoint` 和輸出 `y : FixedPoint` （一開始為零）：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="fdfd1-145">$P （x） = 1 + 2x $ 的結果將會儲存在中 `yFxP` 。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="fdfd1-146">第二個、 `EvaluateEvenPolynomialFxP` 和第三個 `EvaluateOddPolynomialFxP` 分別是偶數和奇數函式的特製化。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="fdfd1-147">也就是說，若是偶數/奇數函數 $f （x） $ 和 $ $ P_ {偶數} （x） = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f （x） $ 可 $P _ {偶數} （x） $ 或 $P _ {奇數} （x）： = x\cdot P_ {偶數} （x） $ 分別為近似值。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="fdfd1-148">在 Q # 中，這兩個案例可以依照下列方式處理：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="fdfd1-149">這會評估 $P _ {偶數} （x） = 1 + 2x ^ 2 $，以及</span><span class="sxs-lookup"><span data-stu-id="fdfd1-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="fdfd1-150">這會評估 $P _ {奇數} （x） = x + 2x ^ 3 $。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="fdfd1-151">其他範例</span><span class="sxs-lookup"><span data-stu-id="fdfd1-151">More samples</span></span>

<span data-ttu-id="fdfd1-152">您可以在[主要範例存放庫](https://github.com/Microsoft/Quantum)中找到更多範例。</span><span class="sxs-lookup"><span data-stu-id="fdfd1-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="fdfd1-153">若要開始使用，請複製存放庫並開啟 `Numerics` 子資料夾：</span><span class="sxs-lookup"><span data-stu-id="fdfd1-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="fdfd1-154">然後， `cd` 放入其中一個範例資料夾，並透過執行範例</span><span class="sxs-lookup"><span data-stu-id="fdfd1-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
