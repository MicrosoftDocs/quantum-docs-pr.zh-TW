---
title: '問 # API 設計原則'
description: '問 # API 設計原則'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426454"
---
# <a name="q-api-design-principles"></a><span data-ttu-id="eabaf-103">問 # API 設計原則</span><span class="sxs-lookup"><span data-stu-id="eabaf-103">Q# API Design Principles</span></span>

## <a name="introduction"></a><span data-ttu-id="eabaf-104">簡介</span><span class="sxs-lookup"><span data-stu-id="eabaf-104">Introduction</span></span>

<span data-ttu-id="eabaf-105">問 # 是一種語言和平臺，可讓使用者撰寫、執行、瞭解及探索量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-105">As a language and as a platform, Q# empowers users to write, run, understand, and explore quantum applications.</span></span>
<span data-ttu-id="eabaf-106">為了加強使用者的能力，當我們設計問 # 程式庫時，我們會遵循一組 API 設計原則來引導我們的設計，並協助我們為「量子開發」社區提供可用的程式庫。</span><span class="sxs-lookup"><span data-stu-id="eabaf-106">In order to empower users, when we design Q# libraries, we follow a set of API design principles to guide our designs and to help us make usable libraries for the the quantum development community.</span></span>
<span data-ttu-id="eabaf-107">本文將列出這些原則，並提供範例，以協助引導您在設計問 # Api 時如何套用它們。</span><span class="sxs-lookup"><span data-stu-id="eabaf-107">This article lists these principles, and gives examples to help guide how to apply them when designing Q# APIs.</span></span>

> [!TIP]
> <span data-ttu-id="eabaf-108">這是相當詳細的檔，旨在協助引導媒體櫃開發和深入的程式庫投稿。</span><span class="sxs-lookup"><span data-stu-id="eabaf-108">This is a fairly detailed document that's intended to help guide library development and in-depth library contributions.</span></span>
> <span data-ttu-id="eabaf-109">如果您是在 Q # 中撰寫自己的程式庫，或在[問 #](https://github.com/microsoft/QuantumLibraries)程式庫中提供較大的功能，您可能會發現它最有用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-109">You'll probably find it most useful if you're writing your own libraries in Q#, or if you're contributing larger features to the [Q# libraries repository](https://github.com/microsoft/QuantumLibraries).</span></span>
>
> <span data-ttu-id="eabaf-110">另一方面，如果您想要瞭解如何更廣泛地參與「量子開發工具組」，建議您從「[貢獻指南](xref:microsoft.quantum.contributing)」開始。</span><span class="sxs-lookup"><span data-stu-id="eabaf-110">On the other hand, if you're looking to learn how to contribute to the Quantum Development Kit more generally, we suggest starting with the [contribution guide](xref:microsoft.quantum.contributing).</span></span>
> <span data-ttu-id="eabaf-111">如果您要尋找有關我們建議如何格式化問 # 程式碼的一般資訊，您可能會想要查看[樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="eabaf-111">If you're looking for more general information about how we recommend formatting your Q# code, you may be interested in checking out the [style guide](xref:microsoft.quantum.contributing.style).</span></span>

## <a name="general-principles"></a><span data-ttu-id="eabaf-112">一般準則</span><span class="sxs-lookup"><span data-stu-id="eabaf-112">General Principles</span></span>

<span data-ttu-id="eabaf-113">**主要原則：** 公開將焦點放在量子應用程式的 Api。</span><span class="sxs-lookup"><span data-stu-id="eabaf-113">**Key principle:** Expose APIs that places the focus on quantum applications.</span></span>

- <span data-ttu-id="eabaf-114">✅**選擇 [** 作業] 和 [函式名稱]，以反映演算法和應用程式的高階結構。</span><span class="sxs-lookup"><span data-stu-id="eabaf-114">✅ **DO** choose operation and function names that reflect the   high-level structure of algorithms and applications.</span></span>
- <span data-ttu-id="eabaf-115">⛔️**不**會公開主要著重于低層級執行詳細資料的 api。</span><span class="sxs-lookup"><span data-stu-id="eabaf-115">⛔️ **DON'T** expose APIs that focus primarily on low-level   implementation details.</span></span>

<span data-ttu-id="eabaf-116">**主要原則：** 使用範例使用案例來啟動每個 API 設計，以確保 Api 可直覺使用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-116">**Key principle:** Start each API design with sample use cases to ensure that APIs are intuitive to use.</span></span>

- <span data-ttu-id="eabaf-117">✅**請確定公用**API 的每個元件都有對應的使用案例，而不是嘗試針對從開始進行的所有可能用法進行設計。</span><span class="sxs-lookup"><span data-stu-id="eabaf-117">✅ **DO** ensure that each component of a public API has a corresponding use case, rather than trying to design for all possible uses from the start.</span></span>
    <span data-ttu-id="eabaf-118">以不同的方式進行，請不要引進公用 Api，以免其有用，但請確定 API 的每個部分都有*具體*的範例，其中會很有用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-118">Put differently, don't introduce public APIs in case they are useful, but make sure that each part of an API has a *concrete* example in which it will be useful.</span></span>

  <span data-ttu-id="eabaf-119">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-119">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-120">@"microsoft.quantum.canon.applytoeachca"可以用來以 `ApplyToEachCA(H, _)` 統一重迭狀態準備暫存器，這是許多配量演算法中的一般工作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-120">@"microsoft.quantum.canon.applytoeachca" can be used as `ApplyToEachCA(H, _)` to prepare registers in a uniform superposition state, a common task in many quantum algorithms.</span></span> <span data-ttu-id="eabaf-121">相同的作業也可以用於準備、數值和 oracle 型演算法中的許多其他工作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-121">The same operation can also be used for many other tasks in preparation, numerics, and oracle-based algorithms.</span></span>

- <span data-ttu-id="eabaf-122">✅**進行**集體討論和研討會新的 API 設計，再次檢查它們是否直覺，並符合建議的使用案例。</span><span class="sxs-lookup"><span data-stu-id="eabaf-122">✅ **DO** brainstorm and workshop new API designs to double-check   that they are intuitive and meet proposed use cases.</span></span>

  <span data-ttu-id="eabaf-123">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-123">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-124">檢查目前 \# 的 Q 代碼，以瞭解新的 API 設計如何簡化並闡明現有的實作為。</span><span class="sxs-lookup"><span data-stu-id="eabaf-124">Inspect current Q\# code to see how new API designs could   simplify and clarify existing implementations.</span></span>
  - <span data-ttu-id="eabaf-125">使用主要物件的代表來審查提議的 API 設計。</span><span class="sxs-lookup"><span data-stu-id="eabaf-125">Review proposed API designs with representatives of primary   audiences.</span></span>

<span data-ttu-id="eabaf-126">**主要原則：** 設計 Api 以支援和鼓勵可讀取的程式碼。</span><span class="sxs-lookup"><span data-stu-id="eabaf-126">**Key principle:** Design APIs to support and encourage readable code.</span></span>

- <span data-ttu-id="eabaf-127">✅**請**確定網域專家和非專家都能讀取程式碼。</span><span class="sxs-lookup"><span data-stu-id="eabaf-127">✅ **DO** ensure that code is readable by domain experts and   non-experts alike.</span></span>
- <span data-ttu-id="eabaf-128">✅**請將焦點放在**高階演算法中每個作業和函式的效果，並使用檔深入探索適當的執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="eabaf-128">✅ **DO** place the focus on the effects of each operation and   function within the high-level algorithm, using documentation to   delve into implementation details as appropriate.</span></span>
- <span data-ttu-id="eabaf-129">✅**請盡可能遵循一般**的問與答[ \# 風格指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="eabaf-129">✅ **DO** follow the common [Q\# style guide](xref:microsoft.quantum.contributing.style) whenever applicable.</span></span>

<span data-ttu-id="eabaf-130">**主要原則：** 將 Api 設計為穩定的，並提供向前相容性。</span><span class="sxs-lookup"><span data-stu-id="eabaf-130">**Key principle:** Design APIs to be stable and to provide forward compatibility.</span></span>

- <span data-ttu-id="eabaf-131">✅當需要中斷性變更時，**請**正常取代舊的 api。</span><span class="sxs-lookup"><span data-stu-id="eabaf-131">✅ **DO** deprecate old APIs gracefully when breaking changes are   required.</span></span>

- <span data-ttu-id="eabaf-132">✅**請**提供「填充碼」作業和函式，讓現有的使用者程式碼在淘汰期間能夠正確運作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-132">✅ **DO** provide "shim" operations and functions that allow   existing user code to operate correctly during deprecation.</span></span>

  <span data-ttu-id="eabaf-133">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-133">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-134">將名為的作業重新命名 `EstimateExpectation` 為時，會引進名為的新作業，此作業 `EstimateAverage` `EstimateExpectation` 會在其新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-134">When renaming an operation called `EstimateExpectation` to   `EstimateAverage`, introduce a new operation called   `EstimateExpectation` that calls the original operation at   its new name, so that existing code can continue to work   correctly.</span></span>

- <span data-ttu-id="eabaf-135">✅**請**務必使用 @"microsoft.quantum.core.deprecated" 屬性，將棄用功能與使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="eabaf-135">✅ **DO** use the @"microsoft.quantum.core.deprecated" attribute to communicate deprecations to the user.</span></span>

- <span data-ttu-id="eabaf-136">✅重新命名作業或函式時，**請**提供新的名稱做為的字串輸入 `@Deprecated` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-136">✅ When renaming an operation or function, **DO** provide the new   name as a string input to `@Deprecated`.</span></span>

- <span data-ttu-id="eabaf-137">⛔️在預覽版本中，**請勿**移除至少六個月後的現有函式或作業，或至少兩年的支援版本。</span><span class="sxs-lookup"><span data-stu-id="eabaf-137">⛔️ **DON'T** remove existing functions or operations without a   deprecation period of at least six months for preview releases,   or at least two years for supported releases.</span></span>

## <a name="functions-and-operations"></a><span data-ttu-id="eabaf-138">函數和作業</span><span class="sxs-lookup"><span data-stu-id="eabaf-138">Functions and Operations</span></span>

<span data-ttu-id="eabaf-139">**主要原則：** 確保每個函式和作業在 API 內都有一個定義完善的目的。</span><span class="sxs-lookup"><span data-stu-id="eabaf-139">**Key principle:** ensure that every function and operation has a single well-defined purpose within the API.</span></span>

- <span data-ttu-id="eabaf-140">⛔️**不**會公開執行多個不相關工作的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="eabaf-140">⛔️ **DON'T** expose functions and operations that perform multiple   unrelated tasks.</span></span>

<span data-ttu-id="eabaf-141">**主要原則：** 盡可能將函式和作業設計為可重複使用，並預期未來的需求。</span><span class="sxs-lookup"><span data-stu-id="eabaf-141">**Key principle:** design functions and operations to be as reusable as possible, and to anticipate future needs.</span></span>

- <span data-ttu-id="eabaf-142">✅**執行**設計函式和作業，以便在相同的 API 和先前現有的程式庫中，與其他函式和作業共同撰寫。</span><span class="sxs-lookup"><span data-stu-id="eabaf-142">✅ **DO** design functions and operations to compose well with other   functions and operations, both in the same API and in previously   existing libraries.</span></span>

  <span data-ttu-id="eabaf-143">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-143">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-144">作業 @"microsoft.quantum.canon.delay" 會對其輸入做出最低的假設，因此可以用來延遲在 Q # 標準程式庫或由使用者定義的任一作業的應用程式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-144">The @"microsoft.quantum.canon.delay" operation makes minimal assumptions about its input, and thus can be used to delay applications of either operations across the Q# standard library or as defined by users.</span></span>
    <!-- TODO: define bad example. -->

- <span data-ttu-id="eabaf-145">✅**確實**會將純粹具決定性的傳統邏輯公開為函式，而不是作業。</span><span class="sxs-lookup"><span data-stu-id="eabaf-145">✅ **DO** expose purely deterministic classical logic as   as functions rather than operations.</span></span>

  <span data-ttu-id="eabaf-146">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-146">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-147">會以決定性的方式寫入其浮點輸入的副程式，因此應該對使用者公開， `Squared : Double -> Double` 而不是做為作業 `Square : Double => Double` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-147">A subroutine which squares its floating-point input can be written deterministically, and so should be exposed to the user as `Squared : Double -> Double` rather than as an operation `Square : Double => Double`.</span></span> <span data-ttu-id="eabaf-148">這可讓您在多個位置呼叫副程式（例如：在其他函式中），並提供實用的優化資訊給編譯器，這可能會影響效能和優化。</span><span class="sxs-lookup"><span data-stu-id="eabaf-148">This allows for the subroutine to be called in more places (e.g.: inside of other functions), and provides useful optimization information to the compiler that can affect performance and optimizations.</span></span>
  - <span data-ttu-id="eabaf-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]`與 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 確定性方面的保證不同，這兩者在不同的情況下都很有用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` and `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` differ in the guarantees made with respect to   determinism; both are useful in different circumstances.</span></span>
  - <span data-ttu-id="eabaf-150">轉換配量作業應用程式的 API 常式通常會以決定性的方式執行，因此可做為函式（例如）來使用 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-150">API routines that transform the application of quantum   operations can often be carried out in a deterministic     fashion and hence can be made available as functions such as   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.</span></span>

- <span data-ttu-id="eabaf-151">✅**請視**需要使用型別參數，將輸入型別一般化為每個函式和運算的合理程度。</span><span class="sxs-lookup"><span data-stu-id="eabaf-151">✅ **DO** generalize the input type as much as reasonable for each   function and operation, using type parameters as needed.</span></span>

  <span data-ttu-id="eabaf-152">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-152">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-153">`ApplyToEach`具有類型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常見應用程式的特定類型 `((Qubit => Unit), Qubit[]) => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-153">`ApplyToEach` has type `<'T>(('T => Unit), 'T[]) => Unit` rather than the specific type of its most common   application, `((Qubit => Unit), Qubit[]) => Unit`.</span></span>

> [!TIP]
> <span data-ttu-id="eabaf-154">請務必預測未來的需求，但針對您的使用者解決具體的問題也很重要。</span><span class="sxs-lookup"><span data-stu-id="eabaf-154">It is important to anticipate future needs, but it is also important to solve concrete problems for your users.</span></span>
> <span data-ttu-id="eabaf-155">因此，基於此主要原則的作用，一律需要謹慎考慮並進行平衡，以避免開發 Api 「以防萬一」。</span><span class="sxs-lookup"><span data-stu-id="eabaf-155">Acting on this key principle thus always requires careful consideration and balancing to avoid developing APIs "just in case."</span></span>

<span data-ttu-id="eabaf-156">索引**鍵原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可以呼叫的目的。</span><span class="sxs-lookup"><span data-stu-id="eabaf-156">**Key principle:** choose input and output types for functions and operations that are predictable, and that communicate the purpose of a callable.</span></span>

- <span data-ttu-id="eabaf-157">✅**請**使用元組類型，以邏輯方式將僅視為重要的輸入和輸出群組在一起。</span><span class="sxs-lookup"><span data-stu-id="eabaf-157">✅ **DO** use tuple types to logically group inputs and outputs that are only significant when considered together.</span></span> <span data-ttu-id="eabaf-158">在這些情況下，請考慮使用使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="eabaf-158">Consider using a user-defined type in these cases.</span></span>

  <span data-ttu-id="eabaf-159">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-159">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-160">輸出另一個函式之本機 minima 的函式可能需要將搜尋間隔的界限當做輸入，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。</span><span class="sxs-lookup"><span data-stu-id="eabaf-160">A function to output the local minima of another function   may need to take bounds of a search interval as input, such   that `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` may be an appropriate signature.</span></span>
  - <span data-ttu-id="eabaf-161">使用參數移位技術來估計機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。</span><span class="sxs-lookup"><span data-stu-id="eabaf-161">An operation to estimate a derivative of a machine learning classifier using the parameter shift technique may need to take both the shifted and unshifted parameter vectors as inputs.</span></span> <span data-ttu-id="eabaf-162">`(unshifted : Double[], shifted : Double[])`在此情況下，類似的輸入可能會很適當。</span><span class="sxs-lookup"><span data-stu-id="eabaf-162">An input similar to `(unshifted : Double[], shifted : Double[])` may be appropriate in this case.</span></span>

- <span data-ttu-id="eabaf-163">✅在不同的函式和作業之間一致地**執行**輸入和輸出元組中的專案順序。</span><span class="sxs-lookup"><span data-stu-id="eabaf-163">✅ **DO** order items in input and output tuples consistently   across different functions and operations.</span></span>

  <span data-ttu-id="eabaf-164">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-164">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-165">如果考慮兩個或函式或作業，其中每個都採用旋轉角度和目標 qubit 做為輸入，請確定在每個輸入元組中，都有相同的排序方式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-165">If considering two or functions or operations that each take a rotation angle and a target qubit as inputs, ensure that they are ordered the same in each input tuple.</span></span> <span data-ttu-id="eabaf-166">也就是， `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 偏好 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 和 `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-166">That is, prefer `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` to `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="eabaf-167">**主要原則：** 設計函式和作業，使其適用于 Q \# 語言功能，例如部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-167">**Key principle:** design functions and operations to work well with Q\# language features such as partial application.</span></span>

- <span data-ttu-id="eabaf-168">✅**請**在輸入元組中執行排序專案，讓最常套用的輸入先發生（也就是：讓部分應用程式的行為類似 currying）。</span><span class="sxs-lookup"><span data-stu-id="eabaf-168">✅ **DO** order items in input tuples such that the most commonly   applied inputs occur first (i.e.: so that partial application   acts similarly to currying).</span></span>

  <span data-ttu-id="eabaf-169">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-169">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-170">使用 `ApplyRotation` 浮點數和 qubit 做為輸入的作業，通常會先與浮點輸入部分一起套用，以搭配預期輸入類型的運算使用 `Qubit => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-170">An operation `ApplyRotation` that takes a floating-point number and a qubit as inputs may often be partially applied with the floating-point input first for use with operations that expect an input of type `Qubit => Unit`.</span></span> <span data-ttu-id="eabaf-171">因此，簽章`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span><span class="sxs-lookup"><span data-stu-id="eabaf-171">Thus, a signature of `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span></span>
      <span data-ttu-id="eabaf-172">會與部分應用程式一致地搭配使用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-172">would work most consistently with partial application.</span></span>
  - <span data-ttu-id="eabaf-173">一般而言，本指南表示將所有傳統資料放在輸入元組的所有 qubits 之前，但請使用良好的判斷，並檢查您的 API 在實務中的呼叫方式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-173">Typically, this guidance means placing all classical data   before all qubits in input tuples, but use good judgment and   examine how your API is called in practice.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="eabaf-174">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="eabaf-174">User-Defined Types</span></span>

<span data-ttu-id="eabaf-175">**主要原則：** 使用使用者定義型別，協助讓 api 更具表達性且方便使用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-175">**Key principle:** use user-defined types to help make APIs more expressive and convenient to use.</span></span>

- <span data-ttu-id="eabaf-176">✅**確實**引進了新的使用者定義型別，以提供有用的冗長和/或複雜型別的速記。</span><span class="sxs-lookup"><span data-stu-id="eabaf-176">✅ **DO** introduce new user-defined types to provide helpful   shorthand for long and/or complicated types.</span></span>

  <span data-ttu-id="eabaf-177">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-177">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-178">如果具有三個 qubit 陣列輸入的作業類型通常會當做輸入或作為輸出傳回，則會提供 UDT，例如`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span><span class="sxs-lookup"><span data-stu-id="eabaf-178">In cases where an operation type with three qubit array inputs is commonly taken as an input or returned as an output, providing a UDT such as `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span></span>
      <span data-ttu-id="eabaf-179">有助於提供有用的速記。</span><span class="sxs-lookup"><span data-stu-id="eabaf-179">can help provide a useful shorthand.</span></span>

- <span data-ttu-id="eabaf-180">✅**確實**會引進新的使用者定義型別，以指出給定的基底型別應該僅用於非常特殊的意義。</span><span class="sxs-lookup"><span data-stu-id="eabaf-180">✅ **DO** introduce new user-defined types to indicate that a given   base type should only be used in a very particular sense.</span></span>

  <span data-ttu-id="eabaf-181">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-181">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-182">應該特別解讀為將傳統資料編碼成量子暫存器的作業，可能適用于具有使用者定義類型的標籤 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-182">An operation that should be interpreted specifically as an   operation that encodes classical data into a quantum   register may be appropriate to label with a user-defined   type `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.</span></span>

- <span data-ttu-id="eabaf-183">✅**請**使用命名專案引進新的使用者定義型別，以允許未來的擴充性（例如：未來可能會包含其他命名專案的結果結構）。</span><span class="sxs-lookup"><span data-stu-id="eabaf-183">✅ **DO** introduce new user-defined types with named items that   allow for future extensibility (e.g.: a results structure that   may contain additional named items in the future).</span></span>

  <span data-ttu-id="eabaf-184">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-184">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-185">當作業 `TrainModel` 公開大量設定選項時，將這些選項公開為新的 `TrainingOptions` UDT 並提供新的函式， `DefaultTrainingOptions : Unit -> TrainingOptions` 可讓使用者覆寫 TrainingOptions UDT 值中的特定已命名專案，同時仍然允許程式庫開發人員視需要加入新的 UDT 專案。</span><span class="sxs-lookup"><span data-stu-id="eabaf-185">When an operation `TrainModel` exposes a large number of   configuration options, exposing these options as a new   `TrainingOptions` UDT and providing a new function   `DefaultTrainingOptions : Unit -> TrainingOptions` allows   users to override specific named items in TrainingOptions   UDT values while still allowing library developers to add   new UDT items as appropriate.</span></span>

- <span data-ttu-id="eabaf-186">✅**請**在喜好設定中，為新的使用者定義類型宣告命名專案，以要求使用者知道正確的元組解構。</span><span class="sxs-lookup"><span data-stu-id="eabaf-186">✅ **DO** declare named items for new user-defined types in   preference to requiring users to know the correct tuple   deconstruction.</span></span>

  <span data-ttu-id="eabaf-187">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-187">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-188">在其極座標分解中表示覆數時，偏好 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 使用 `newtype ComplexPolar = (Double, Double)` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-188">When representing a complex number in its polar   decomposition, prefer   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` to   `newtype ComplexPolar = (Double, Double)`.</span></span>

<span data-ttu-id="eabaf-189">**主要原則：** 使用使用者定義型別，方法是減少認知負載，而不需要使用者學習其他概念和命名法。</span><span class="sxs-lookup"><span data-stu-id="eabaf-189">**Key principle:** use user-defined types in ways reduce  cognitive load and that don't require the user to learn additional concepts and nomenclature.</span></span>

- <span data-ttu-id="eabaf-190">⛔️**不**會引進使用者定義的型別，要求使用者經常使用解除包裝運算子（ `!` ），或通常需要多個解除包裝的層級。</span><span class="sxs-lookup"><span data-stu-id="eabaf-190">⛔️ **DON'T** introduce user-defined types that require the user to make frequent use of the unwrap operator (`!`), or that commonly require multiple levels of unwrapping.</span></span> <span data-ttu-id="eabaf-191">可能的緩和策略包括：</span><span class="sxs-lookup"><span data-stu-id="eabaf-191">Possible mitigation strategies include:</span></span>

  - <span data-ttu-id="eabaf-192">以單一專案公開使用者定義的型別時，請考慮定義該專案的名稱。</span><span class="sxs-lookup"><span data-stu-id="eabaf-192">When exposing a user-defined type with a single item, consider defining a name for that item.</span></span> <span data-ttu-id="eabaf-193">例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 將偏好設定為 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-193">For instance, consider `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` in preference to `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.</span></span>

  - <span data-ttu-id="eabaf-194">確保其他函數和作業可以直接接受「包裝的」 UDT 實例。</span><span class="sxs-lookup"><span data-stu-id="eabaf-194">Ensuring that other functions and operations can accept   "wrapped" UDT instances directly.</span></span>

- <span data-ttu-id="eabaf-195">⛔️**不**會導入重複內建類型的新使用者定義類型，而不會提供其他表達。</span><span class="sxs-lookup"><span data-stu-id="eabaf-195">⛔️ **DON'T** introduce new user-defined types that duplicate   built-in types without providing additional expressiveness.</span></span>

  <span data-ttu-id="eabaf-196">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-196">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-197">UDT `newtype QubitRegister = Qubit[]` 不提供任何額外的表達 `Qubit[]` ，因此很難使用，而且不會有明顯的好處。</span><span class="sxs-lookup"><span data-stu-id="eabaf-197">A UDT `newtype QubitRegister = Qubit[]` provides no   additional expressiveness over `Qubit[]`, and is thus harder   to use with no discernable benefit.</span></span>
  - <span data-ttu-id="eabaf-198">UDT 會 `newtype LittleEndian = Qubit[]` 記錄基礎暫存器的使用和解讀方式，因此會提供其基底類型的其他表達。</span><span class="sxs-lookup"><span data-stu-id="eabaf-198">A UDT `newtype LittleEndian = Qubit[]` documents how the   underlying register is to be used and interpreted, and thus   provides additional expressiveness over its base type.</span></span>

- <span data-ttu-id="eabaf-199">除非絕對必要，否則⛔️**不**引進存取子函式;  在此情況下，強烈偏好命名專案。</span><span class="sxs-lookup"><span data-stu-id="eabaf-199">⛔️ **DON'T** introduce accessor functions unless strictly required;   strongly prefer named items in this case.</span></span>

  <span data-ttu-id="eabaf-200">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-200">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-201">引進 UDT 時，建議您將 `newtype Complex = (Double, Double)` 定義修改為， `newtype Complex = (Real : Double, Imag : Double)` 以引進函數 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-201">When introducing a UDT `newtype Complex = (Double, Double)`,   prefer modifying the definition to   `newtype Complex = (Real : Double, Imag : Double)` to introducing   functions `GetReal : Complex -> Double` and   `GetImag : Complex -> Double`.</span></span>

## <a name="namespaces-and-organization"></a><span data-ttu-id="eabaf-202">命名空間和組織</span><span class="sxs-lookup"><span data-stu-id="eabaf-202">Namespaces and Organization</span></span>

<span data-ttu-id="eabaf-203">**主要原則：** 選擇可預測的命名空間名稱，並在每個命名空間中清楚地傳達函數、作業和使用者定義類型的用途。</span><span class="sxs-lookup"><span data-stu-id="eabaf-203">**Key principle:** choose namespace names that are predictable and that clearly communicate the purpose of functions, operations, and user-defined types in each namespace.</span></span>

- <span data-ttu-id="eabaf-204">✅將命名**空間命名為** `Publisher.Product.DomainArea` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-204">✅ **DO** name namespaces as `Publisher.Product.DomainArea`.</span></span>

  <span data-ttu-id="eabaf-205">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-205">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-206">由 Microsoft 發佈的函式、作業和 Udt，屬於量子開發工具組的量子模擬功能，會放在 `Microsoft.Quantum.Simulation` 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="eabaf-206">Functions, operations, and UDTs published by Microsoft as a   part of the quantum simulation feature of the Quantum   Development Kit are placed in the   `Microsoft.Quantum.Simulation` namespace.</span></span>
  - <span data-ttu-id="eabaf-207">`Microsoft.Quantum.Math`代表 Microsoft 發佈的命名空間，做為與數學網域區域相關的量子開發工具組的一部分。</span><span class="sxs-lookup"><span data-stu-id="eabaf-207">`Microsoft.Quantum.Math` represents a namespace   published by Microsoft as part of the Quantum Development   Kit pertaining to the mathematics domain area.</span></span>

- <span data-ttu-id="eabaf-208">✅**將用於**特定功能的作業、函式和使用者定義類型，放在描述該功能的命名空間中，即使該功能是在不同的問題網域之間使用，也可以。</span><span class="sxs-lookup"><span data-stu-id="eabaf-208">✅ **DO** place operations, functions, and user-defined types used   for specific functionality into a namespace that describes that   functionality, even when that functionality is used across   different problem domains.</span></span>

  <span data-ttu-id="eabaf-209">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-209">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-210">Microsoft 發佈的狀態準備 Api 會放入，以作為「量子開發工具組」的一部分 `Microsoft.Quantum.Preparation` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-210">State preparation APIs published by Microsoft as a part of   the Quantum Development Kit would be placed into   `Microsoft.Quantum.Preparation`.</span></span>
  - <span data-ttu-id="eabaf-211">Microsoft 在配量開發工具組中發佈的量子模擬 Api 會放入中 `Microsoft.Quantum.Simulation` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-211">Quantum simulation APIs published by Microsoft as a part of the Quantum   Development Kit would be placed into   `Microsoft.Quantum.Simulation`.</span></span>

- <span data-ttu-id="eabaf-212">✅**請將僅**在特定網域內使用的作業、函式和使用者定義類型，放入表示其公用程式網域的命名空間。</span><span class="sxs-lookup"><span data-stu-id="eabaf-212">✅ **DO** place operations, functions, and user-defined types used only within specific domains into namespaces indicating their domain of utility.</span></span> <span data-ttu-id="eabaf-213">如有需要，請使用子命名空間來指示每個網域特定命名空間中的焦點工作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-213">If needed, use subnamespaces to indicate focused tasks within each domain-specific namespace.</span></span>

  <span data-ttu-id="eabaf-214">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-214">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-215">Microsoft 所發佈的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets" 命名空間所提供。</span><span class="sxs-lookup"><span data-stu-id="eabaf-215">The quantum machine learning library published by Microsoft is largely   placed into the @"microsoft.quantum.machinelearning" namespace, but example   datasets are provided by the @"microsoft.quantum.machinelearning.datasets"   namespace.</span></span>
  - <span data-ttu-id="eabaf-216">由 Microsoft 在配量開發工具組中發佈的量子化學 Api 應放入中 `Microsoft.Quantum.Chemistry` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-216">Quantum chemistry APIs published by Microsoft as a part of the Quantum Development Kit should be placed into `Microsoft.Quantum.Chemistry`.</span></span> <span data-ttu-id="eabaf-217">執行約旦--Wigner 分解特有的功能可以放在中 `Microsoft.Quantum.Chemistry.JordanWigner` ，讓 [量子化學] 領域區域的主要介面不會與實作為顧慮。</span><span class="sxs-lookup"><span data-stu-id="eabaf-217">Functionality specific to implementing the Jordan--Wigner decomposition may be placed in `Microsoft.Quantum.Chemistry.JordanWigner`, so that the primary interface for the quantum chemistry domain area is not concerned with implementations.</span></span>

<span data-ttu-id="eabaf-218">**主要原則：** 將命名空間和存取修飾詞一起使用，以刻意瞭解對使用者公開的 API 介面，並隱藏與 Api 的執行和測試相關的內部詳細資料。</span><span class="sxs-lookup"><span data-stu-id="eabaf-218">**Key principle:** Use namespaces and access modifiers together to be intentional about the API surface exposed to users, and to hide internal details related to implementation and testing of your APIs.</span></span>

- <span data-ttu-id="eabaf-219">✅在合理的情況下，請將將 API 實作為所實作為 API 的相同命名空間，將所需的所有函式和作業**都放入**，但以 "private" 或 "internal" 關鍵字標示，表示它們不是程式庫公用 API 介面的一部分。</span><span class="sxs-lookup"><span data-stu-id="eabaf-219">✅ Whenever reasonable, **DO** place all functions and operations needed to implement an API into the same namespace as the API being implemented, but marked with the "private" or "internal" keywords to indicate that they are not part of the public API surface for a library.</span></span> <span data-ttu-id="eabaf-220">使用開頭為底線（）的名稱 `_` ，以視覺方式區分私用和內部作業和公用 callables 的函式。</span><span class="sxs-lookup"><span data-stu-id="eabaf-220">Use a name beginning with an underscore (`_`) to visually distinguish private and internal operations and functions from public callables.</span></span>

  <span data-ttu-id="eabaf-221">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-221">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-222">作業名稱 `_Features` 會指出特定命名空間和元件的私用函式，而且應該伴隨 `internal` 關鍵字。</span><span class="sxs-lookup"><span data-stu-id="eabaf-222">The operation name `_Features` indicates a function that is   private to a given namespace and assembly, and should be   accompanied by either the `internal` keyword.</span></span>

- <span data-ttu-id="eabaf-223">✅在很罕見的情況下，若要為指定的命名空間執行 API，請將**它們放在**符合所實和結尾之命名空間的新命名空間中 `.Private` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-223">✅ In the rare case that an extensive set of private functions or operations are needed to implement the API for a given namespace, **DO** place them in a new namespace matching the namespace being implemented and ending in `.Private`.</span></span>

- <span data-ttu-id="eabaf-224">✅**將所有**單元測試都放入符合受測命名空間的命名空間中，並以結尾 `.Tests` 。</span><span class="sxs-lookup"><span data-stu-id="eabaf-224">✅ **DO** place all unit tests into namespaces matching the     namespace under test and ending in `.Tests`.</span></span>

## <a name="naming-conventions-and-vocabulary"></a><span data-ttu-id="eabaf-225">命名慣例和詞彙</span><span class="sxs-lookup"><span data-stu-id="eabaf-225">Naming Conventions and Vocabulary</span></span>

<span data-ttu-id="eabaf-226">**主要原則：** 在各種不同的物件上選擇清楚、可存取且可讀取的名稱和詞彙，包括量子新手和專家。</span><span class="sxs-lookup"><span data-stu-id="eabaf-226">**Key principle:** Choose names and terminology that are clear, accessible, and readable across a diverse range of audiences, including both quantum novices and experts.</span></span>

- <span data-ttu-id="eabaf-227">⛔️**不**會使用歧視性或 exclusionary 識別碼名稱，也不會有 API 檔批註的術語。</span><span class="sxs-lookup"><span data-stu-id="eabaf-227">⛔️ **DON'T** use discriminatory or exclusionary identifier names,   nor terminology in API documentation comments.</span></span>

- <span data-ttu-id="eabaf-228">✅**請務必使用 API**檔批註來提供相關的內容、範例和參考，特別是針對更棘手的概念。</span><span class="sxs-lookup"><span data-stu-id="eabaf-228">✅ **DO** use API documentation comments to provide relevant   context, examples, and references, especially for more difficult   concepts.</span></span>

- <span data-ttu-id="eabaf-229">⛔️**不**會使用不必要難理解的識別碼名稱，或需要重要的量子演算法知識才能讀取。</span><span class="sxs-lookup"><span data-stu-id="eabaf-229">⛔️ **DON'T** use identifier names that are unnecessarily esoteric,   or that require significant quantum algorithms knowledge to   read.</span></span>

  <span data-ttu-id="eabaf-230">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-230">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-231">偏好將「波幅放大反復專案」設為「Grover 反復專案」。</span><span class="sxs-lookup"><span data-stu-id="eabaf-231">Prefer "amplitude amplification iteration" to "Grover   iteration."</span></span>

- <span data-ttu-id="eabaf-232">✅**請**選擇作業和函式名稱，以清楚地傳達所需的可呼叫效果，而不是其實作為。</span><span class="sxs-lookup"><span data-stu-id="eabaf-232">✅ **DO** choose operations and function names that clearly communicate the intended effect of a callable, and not its implementation.</span></span> <span data-ttu-id="eabaf-233">請注意，您可以在[API 檔批註](xref:microsoft.quantum.guide.filestructure#documentation-comments)中記載和執行。</span><span class="sxs-lookup"><span data-stu-id="eabaf-233">Note that the implementation can and should be documented in [API documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments).</span></span>

  <span data-ttu-id="eabaf-234">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-234">*Examples:*</span></span>
  - <span data-ttu-id="eabaf-235">偏好「估計重迭」為「Hadamard 測試」，因為後者會傳達前者的實值。</span><span class="sxs-lookup"><span data-stu-id="eabaf-235">Prefer "estimate overlap" to "Hadamard test," as the latter   communicates how the former is implemented.</span></span>

- <span data-ttu-id="eabaf-236">✅在所有 Q api 中，以一致的**方式使用單字** \# ：</span><span class="sxs-lookup"><span data-stu-id="eabaf-236">✅ **DO** use words in a consistent fashion across all Q\# APIs:</span></span>

  - <span data-ttu-id="eabaf-237">**之外**</span><span class="sxs-lookup"><span data-stu-id="eabaf-237">**Verbs:**</span></span>

    - <span data-ttu-id="eabaf-238">判斷**提示：檢查**有關目的電腦及其 qubits 狀態的假設，可能是使用 unphysical 資源。</span><span class="sxs-lookup"><span data-stu-id="eabaf-238">**Assert**: Check that an assumption about the state of a target machine and its qubits holds, possibly by using unphysical resources.</span></span> <span data-ttu-id="eabaf-239">使用此動詞命令的作業應一律安全地卸載，而不會影響程式庫和可執行程式的功能。</span><span class="sxs-lookup"><span data-stu-id="eabaf-239">Operations using this verb should always be safely removable without affecting the functionality of libraries and executable programs.</span></span> <span data-ttu-id="eabaf-240">請注意，與事實不同的是，判斷提示一般可能會依賴外部狀態，例如 qubit 暫存器的狀態、執行環境等等。</span><span class="sxs-lookup"><span data-stu-id="eabaf-240">Note that unlike facts, assertions may in general depend on external state, such as the state of a qubit register, the execution environment or so forth.</span></span> <span data-ttu-id="eabaf-241">因為對外部狀態的相依性是一種副作用，所以判斷提示必須公開為作業，而不是函數。</span><span class="sxs-lookup"><span data-stu-id="eabaf-241">As dependency on external state is a kind of side effect, assertions must be exposed as operations rather than functions.</span></span>

    - <span data-ttu-id="eabaf-242">**估計**：使用一或多個可能重複的測量，從測量結果估計傳統數量。</span><span class="sxs-lookup"><span data-stu-id="eabaf-242">**Estimate**: Using one or more possibly repeated   measurements, estimate a classical quantity from   measurement results.</span></span>

      <span data-ttu-id="eabaf-243">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-243">*Examples:*</span></span>
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - <span data-ttu-id="eabaf-244">**準備**：將配量作業或作業順序套用至一或多個假設以特定初始狀態啟動的 qubits （通常是 $ \ket{00\cdots 0} $），這會導致這些 qubits 的狀態演變成所需的結束狀態。</span><span class="sxs-lookup"><span data-stu-id="eabaf-244">**Prepare**: Apply a quantum operation or sequence of operations to one or more qubits assumed to start in a particular initial state (typically $\ket{00\cdots 0}$), causing the state of those qubits to evolve to a desired end state.</span></span> <span data-ttu-id="eabaf-245">一般來說，在指定的啟動狀態以外的狀態下，**可能會**產生未定義的單一轉換，但仍**應**保留作業及其 adjoint 的「取消」並套用非 op。</span><span class="sxs-lookup"><span data-stu-id="eabaf-245">In general, acting on states other than the given starting state **MAY** result in an undefined unitary transformation, but **SHOULD** still preserve that an operation and its adjoint "cancel out" and apply a no-op.</span></span>

      <span data-ttu-id="eabaf-246">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-246">*Examples:*</span></span>
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - <span data-ttu-id="eabaf-247">**量值**：將配量作業或作業順序套用至一或多個 qubits，並讀取傳統資料。</span><span class="sxs-lookup"><span data-stu-id="eabaf-247">**Measure**: Apply a quantum operation or sequence of   operations to one or more qubits, reading classical data   back out.</span></span>

      <span data-ttu-id="eabaf-248">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-248">*Examples:*</span></span>
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - <span data-ttu-id="eabaf-249">**Apply**：將配量作業或作業順序套用至一或多個 qubits，使這些 qubits 的狀態以一致的方式變更。</span><span class="sxs-lookup"><span data-stu-id="eabaf-249">**Apply**: Apply a quantum operation or sequence of operations to one or more qubits, causing the state of those qubits to change in a coherent fashion.</span></span> <span data-ttu-id="eabaf-250">這個動詞是 Q 命名法中最常見的動詞 \# ，**不應**在更特定的動詞更直接相關時使用。</span><span class="sxs-lookup"><span data-stu-id="eabaf-250">This verb is the most general verb in Q\# nomenclature, and **SHOULD NOT BE** used when a more specific verb is more directly relevant.</span></span>

  - <span data-ttu-id="eabaf-251">**名詞**：</span><span class="sxs-lookup"><span data-stu-id="eabaf-251">**Nouns**:</span></span>

    - <span data-ttu-id="eabaf-252">**事實**：僅取決於其輸入，而不是目的電腦的狀態、其環境或電腦 qubits 狀態的布林值條件。</span><span class="sxs-lookup"><span data-stu-id="eabaf-252">**Fact**: A Boolean condition which depends only on its inputs and not on the state of a target machine, its environment, or the state of the machine's qubits.</span></span> <span data-ttu-id="eabaf-253">相較于判斷提示，事實只對提供給該事實的*值*是敏感的。</span><span class="sxs-lookup"><span data-stu-id="eabaf-253">By contrast with an assertion, a fact is only sensitive to the *values* provided to that fact.</span></span> <span data-ttu-id="eabaf-254">例如：</span><span class="sxs-lookup"><span data-stu-id="eabaf-254">For example:</span></span>

      <span data-ttu-id="eabaf-255">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-255">*Examples:*</span></span>
      - <span data-ttu-id="eabaf-256">@"microsoft.quantum.diagnostics.equalityfacti"：表示兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或不會與任何其他程式狀態無關。</span><span class="sxs-lookup"><span data-stu-id="eabaf-256">@"microsoft.quantum.diagnostics.equalityfacti": represents an equality fact about two integer inputs; either the integers provided as input are equal to each other, or they are not, independent of any other program state.</span></span>

    - <span data-ttu-id="eabaf-257">**選項：** UDT，其中包含數個命名專案，可以做為函式或作業的「選擇性引數」。</span><span class="sxs-lookup"><span data-stu-id="eabaf-257">**Options:** A UDT containing several named items that can act as "optional arguments" to a function or operation.</span></span> <span data-ttu-id="eabaf-258">例如：</span><span class="sxs-lookup"><span data-stu-id="eabaf-258">For example:</span></span>

      <span data-ttu-id="eabaf-259">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-259">*Examples:*</span></span>
      - <span data-ttu-id="eabaf-260">@"microsoft.quantum.machinelearning.trainingoptions"UDT 包含學習速率的命名專案、迷你批次大小，以及適用于 ML 訓練的其他可設定參數。</span><span class="sxs-lookup"><span data-stu-id="eabaf-260">The @"microsoft.quantum.machinelearning.trainingoptions" UDT includes named items for learning rate, minibatch size, and other configurable parameters for ML training.</span></span>

  - <span data-ttu-id="eabaf-261">**形容詞**：</span><span class="sxs-lookup"><span data-stu-id="eabaf-261">**Adjectives**:</span></span>

    - <span data-ttu-id="eabaf-262">⛔️ **New**：**不應**使用此形容詞，以避免在許多程式設計語言中將其使用方式與動詞（例如： c + +、c #、JAVA、TypeScript、PowerShell）混淆。</span><span class="sxs-lookup"><span data-stu-id="eabaf-262">⛔️ **New**: This adjective **SHOULD NOT** be used, as to avoid confusion   with its usage as a verb in many   programming languages (e.g.: C++, C#, Java, TypeScript, PowerShell).</span></span>

  - <span data-ttu-id="eabaf-263">**介係詞：** 在某些情況下，介係詞可以用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。</span><span class="sxs-lookup"><span data-stu-id="eabaf-263">**Prepositions:** In some cases, prepositions can be used to further disambiguate or clarify the roles of nouns and verbs in function and operation names.</span></span> <span data-ttu-id="eabaf-264">不過，請務必謹慎且一致地採取此動作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-264">Care should be taken to do so sparingly and consistently, however.</span></span>

    - <span data-ttu-id="eabaf-265">**As：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示**為** *X* ，而不是其原始標記法。</span><span class="sxs-lookup"><span data-stu-id="eabaf-265">**As:** Represents that a function's input and output represent the same information, but that the output represents that information **as** an *X* instead of its original representation.</span></span> <span data-ttu-id="eabaf-266">這對於型別轉換函式而言特別常見。</span><span class="sxs-lookup"><span data-stu-id="eabaf-266">This is especially common for type conversion functions.</span></span>

      <span data-ttu-id="eabaf-267">*範例：*</span><span class="sxs-lookup"><span data-stu-id="eabaf-267">*Examples:*</span></span>
      - <span data-ttu-id="eabaf-268">`IntAsDouble(2)`表示輸入（ `2` ）和輸出（ `2.0` ）都代表品質相同的資訊，但使用不同的 Q \# 資料類型來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="eabaf-268">`IntAsDouble(2)` indicates that both the input (`2`) and the output (`2.0`)   represent qualitatively the same information, but using   different Q\# data types to do so.</span></span>

    - <span data-ttu-id="eabaf-269">**來源：** 若要確保一致性，此介係詞**不應該**用來表示類型轉換函式，或任何其他**適合的情況**。</span><span class="sxs-lookup"><span data-stu-id="eabaf-269">**From:** To ensure consistency, this preposition   **SHOULD NOT** be used to indicate type conversion   functions or any other case where **As** is appropriate.</span></span>

    - <span data-ttu-id="eabaf-270">⛔️**為：** **不應**使用此介係詞，因為它會與許多程式設計語言中的動詞一起使用，以避免混淆。</span><span class="sxs-lookup"><span data-stu-id="eabaf-270">⛔️ **To:** This preposition **SHOULD NOT** be used, as to   avoid confusion with its usage as a verb in many   programming languages.</span></span>
