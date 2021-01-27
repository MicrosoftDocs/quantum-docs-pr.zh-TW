---
title: Q# API 設計原則
description: Q# API 設計原則
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 452b32141dc660acbe8ef28530f1430e5acff9aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856693"
---
# <a name="no-locq-api-design-principles"></a><span data-ttu-id="37c18-103">Q# API 設計原則</span><span class="sxs-lookup"><span data-stu-id="37c18-103">Q# API Design Principles</span></span>

## <a name="introduction"></a><span data-ttu-id="37c18-104">簡介</span><span class="sxs-lookup"><span data-stu-id="37c18-104">Introduction</span></span>

<span data-ttu-id="37c18-105">作為一種語言和平臺，讓 Q# 使用者能夠撰寫、執行、瞭解和探索量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="37c18-105">As a language and as a platform, Q# empowers users to write, run, understand, and explore quantum applications.</span></span>
<span data-ttu-id="37c18-106">為了讓使用者能夠使用，當我們設計 Q# 程式庫時，我們會遵循一組 API 設計原則來引導我們的設計，並協助我們為量子開發社區提供可用的程式庫。</span><span class="sxs-lookup"><span data-stu-id="37c18-106">In order to empower users, when we design Q# libraries, we follow a set of API design principles to guide our designs and to help us make usable libraries for the the quantum development community.</span></span>
<span data-ttu-id="37c18-107">本文將列出這些原則，並提供範例來說明如何在設計 api 時套用這些原則 Q# 。</span><span class="sxs-lookup"><span data-stu-id="37c18-107">This article lists these principles, and gives examples to help guide how to apply them when designing Q# APIs.</span></span>

> [!TIP]
> <span data-ttu-id="37c18-108">這是一份相當詳細的檔，旨在協助引導程式庫開發和深度程式庫投稿。</span><span class="sxs-lookup"><span data-stu-id="37c18-108">This is a fairly detailed document that's intended to help guide library development and in-depth library contributions.</span></span>
> <span data-ttu-id="37c18-109">如果您要在中撰寫自己的程式庫，或在程式庫存放庫中提供 Q# 較大的功能，您[ Q# ](https://github.com/microsoft/QuantumLibraries)可能會發現它最有用。</span><span class="sxs-lookup"><span data-stu-id="37c18-109">You'll probably find it most useful if you're writing your own libraries in Q#, or if you're contributing larger features to the [Q# libraries repository](https://github.com/microsoft/QuantumLibraries).</span></span>
>
> <span data-ttu-id="37c18-110">相反地，如果您想要瞭解如何更普遍地參與量子開發工具組，我們建議您從 [貢獻指南](xref:microsoft.quantum.contributing)開始。</span><span class="sxs-lookup"><span data-stu-id="37c18-110">On the other hand, if you're looking to learn how to contribute to the Quantum Development Kit more generally, we suggest starting with the [contribution guide](xref:microsoft.quantum.contributing).</span></span>
> <span data-ttu-id="37c18-111">如果您要尋找更多有關如何建議您格式化程式碼的一般資訊 Q# ，您可能會想要查看 [樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="37c18-111">If you're looking for more general information about how we recommend formatting your Q# code, you may be interested in checking out the [style guide](xref:microsoft.quantum.contributing.style).</span></span>

## <a name="general-principles"></a><span data-ttu-id="37c18-112">一般準則</span><span class="sxs-lookup"><span data-stu-id="37c18-112">General Principles</span></span>

<span data-ttu-id="37c18-113">**主要原則：** 公開將焦點放在量子應用程式上的 Api。</span><span class="sxs-lookup"><span data-stu-id="37c18-113">**Key principle:** Expose APIs that places the focus on quantum applications.</span></span>

- <span data-ttu-id="37c18-114">✅**請** 選擇可反映演算法和應用程式高層級結構的作業和函式名稱。</span><span class="sxs-lookup"><span data-stu-id="37c18-114">✅ **DO** choose operation and function names that reflect the   high-level structure of algorithms and applications.</span></span>
- <span data-ttu-id="37c18-115">⛔️ **不** 會公開焦點主要在低層級的執行詳細資料上的 api。</span><span class="sxs-lookup"><span data-stu-id="37c18-115">⛔️ **DON'T** expose APIs that focus primarily on low-level   implementation details.</span></span>

<span data-ttu-id="37c18-116">**主要原則：** 使用範例使用案例來開始每個 API 設計，以確保 Api 可直覺化。</span><span class="sxs-lookup"><span data-stu-id="37c18-116">**Key principle:** Start each API design with sample use cases to ensure that APIs are intuitive to use.</span></span>

- <span data-ttu-id="37c18-117">✅**確定公用** API 的每個元件都有相對應的使用案例，而不是嘗試針對所有可能的使用方式進行設計。</span><span class="sxs-lookup"><span data-stu-id="37c18-117">✅ **DO** ensure that each component of a public API has a corresponding use case, rather than trying to design for all possible uses from the start.</span></span>
    <span data-ttu-id="37c18-118">以不同的方式放置，如果公用 Api 很有用，請不要引進公用 Api，但請確定 API 的每個部分都有 *具體* 的範例，其中將會很有用。</span><span class="sxs-lookup"><span data-stu-id="37c18-118">Put differently, don't introduce public APIs in case they are useful, but make sure that each part of an API has a *concrete* example in which it will be useful.</span></span>

  <span data-ttu-id="37c18-119">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-119">*Examples:*</span></span>
  - <span data-ttu-id="37c18-120">@"microsoft.quantum.canon.applytoeachca" 可以用 `ApplyToEachCA(H, _)` 來準備在統一迭加狀態中的暫存器，也就是許多量子演算法中常見的工作。</span><span class="sxs-lookup"><span data-stu-id="37c18-120">@"microsoft.quantum.canon.applytoeachca" can be used as `ApplyToEachCA(H, _)` to prepare registers in a uniform superposition state, a common task in many quantum algorithms.</span></span> <span data-ttu-id="37c18-121">相同的作業也可以用於準備、數值和 oracle 演算法的許多其他工作。</span><span class="sxs-lookup"><span data-stu-id="37c18-121">The same operation can also be used for many other tasks in preparation, numerics, and oracle-based algorithms.</span></span>

- <span data-ttu-id="37c18-122">✅**進行** 集體討論並研討會新的 API 設計，以再次檢查它們是否直覺，並符合建議的使用案例。</span><span class="sxs-lookup"><span data-stu-id="37c18-122">✅ **DO** brainstorm and workshop new API designs to double-check   that they are intuitive and meet proposed use cases.</span></span>

  <span data-ttu-id="37c18-123">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-123">*Examples:*</span></span>
  - <span data-ttu-id="37c18-124">檢查目前的 Q 程式 \# 代碼，以瞭解新的 API 設計如何簡化和闡明現有的實作為。</span><span class="sxs-lookup"><span data-stu-id="37c18-124">Inspect current Q\# code to see how new API designs could   simplify and clarify existing implementations.</span></span>
  - <span data-ttu-id="37c18-125">使用主要物件的代表來審核提議的 API 設計。</span><span class="sxs-lookup"><span data-stu-id="37c18-125">Review proposed API designs with representatives of primary   audiences.</span></span>

<span data-ttu-id="37c18-126">**主要原則：** 設計 Api 來支援和鼓勵可讀取的程式碼。</span><span class="sxs-lookup"><span data-stu-id="37c18-126">**Key principle:** Design APIs to support and encourage readable code.</span></span>

- <span data-ttu-id="37c18-127">✅**請** 確定網域專家和非專家都可讀取程式碼。</span><span class="sxs-lookup"><span data-stu-id="37c18-127">✅ **DO** ensure that code is readable by domain experts and   non-experts alike.</span></span>
- <span data-ttu-id="37c18-128">✅**請將焦點** 放在高階演算法內的每個作業和功能的效果，並使用檔以適當的方式深入探索執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="37c18-128">✅ **DO** place the focus on the effects of each operation and   function within the high-level algorithm, using documentation to   delve into implementation details as appropriate.</span></span>
- <span data-ttu-id="37c18-129">✅**請遵循常見** 的 [Q \# 樣式指南](xref:microsoft.quantum.contributing.style)（如果適用）。</span><span class="sxs-lookup"><span data-stu-id="37c18-129">✅ **DO** follow the common [Q\# style guide](xref:microsoft.quantum.contributing.style) whenever applicable.</span></span>

<span data-ttu-id="37c18-130">**主要原則：** 將 Api 設計為穩定，並提供向前相容性。</span><span class="sxs-lookup"><span data-stu-id="37c18-130">**Key principle:** Design APIs to be stable and to provide forward compatibility.</span></span>

- <span data-ttu-id="37c18-131">✅需要中斷變更時， **請確實** 取代舊的 api。</span><span class="sxs-lookup"><span data-stu-id="37c18-131">✅ **DO** deprecate old APIs gracefully when breaking changes are   required.</span></span>

- <span data-ttu-id="37c18-132">✅**請** 提供「填充碼」作業和函式，以允許現有使用者程式碼在淘汰期間正常運作。</span><span class="sxs-lookup"><span data-stu-id="37c18-132">✅ **DO** provide "shim" operations and functions that allow   existing user code to operate correctly during deprecation.</span></span>

  <span data-ttu-id="37c18-133">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-133">*Examples:*</span></span>
  - <span data-ttu-id="37c18-134">將呼叫的作業重新命名時 `EstimateExpectation`   `EstimateAverage` ，會引入名為的新作業，該作業會   `EstimateExpectation` 以新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。</span><span class="sxs-lookup"><span data-stu-id="37c18-134">When renaming an operation called `EstimateExpectation` to   `EstimateAverage`, introduce a new operation called   `EstimateExpectation` that calls the original operation at   its new name, so that existing code can continue to work   correctly.</span></span>

- <span data-ttu-id="37c18-135">✅**請** 使用 @"microsoft.quantum.core.deprecated" 屬性將棄用功能傳達給使用者。</span><span class="sxs-lookup"><span data-stu-id="37c18-135">✅ **DO** use the @"microsoft.quantum.core.deprecated" attribute to communicate deprecations to the user.</span></span>

- <span data-ttu-id="37c18-136">✅ 重新命名作業或函式時，請提供新的名稱 **做** 為的字串輸入 `@Deprecated` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-136">✅ When renaming an operation or function, **DO** provide the new   name as a string input to `@Deprecated`.</span></span>

- <span data-ttu-id="37c18-137">⛔️ **不** 會移除現有的函式或作業，但在預覽版本中，至少有六個月的淘汰期，或至少兩年的支援版本。</span><span class="sxs-lookup"><span data-stu-id="37c18-137">⛔️ **DON'T** remove existing functions or operations without a   deprecation period of at least six months for preview releases,   or at least two years for supported releases.</span></span>

## <a name="functions-and-operations"></a><span data-ttu-id="37c18-138">函數和作業</span><span class="sxs-lookup"><span data-stu-id="37c18-138">Functions and Operations</span></span>

<span data-ttu-id="37c18-139">**主要原則：** 確定每個函式和作業在 API 內都有一個定義完善的用途。</span><span class="sxs-lookup"><span data-stu-id="37c18-139">**Key principle:** ensure that every function and operation has a single well-defined purpose within the API.</span></span>

- <span data-ttu-id="37c18-140">⛔️ **不** 會公開執行多個不相關工作的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="37c18-140">⛔️ **DON'T** expose functions and operations that perform multiple   unrelated tasks.</span></span>

<span data-ttu-id="37c18-141">**主要原則：** 盡可能將函式和作業設計為可重複使用，並預測未來的需要。</span><span class="sxs-lookup"><span data-stu-id="37c18-141">**Key principle:** design functions and operations to be as reusable as possible, and to anticipate future needs.</span></span>

- <span data-ttu-id="37c18-142">✅請在相同的 API 和先前現有的程式庫中， **進行** 設計功能和作業，以與其他函式和作業一起撰寫。</span><span class="sxs-lookup"><span data-stu-id="37c18-142">✅ **DO** design functions and operations to compose well with other   functions and operations, both in the same API and in previously   existing libraries.</span></span>

  <span data-ttu-id="37c18-143">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-143">*Examples:*</span></span>
  - <span data-ttu-id="37c18-144">作業 @"microsoft.quantum.canon.delay" 會對其輸入進行最基本的假設，因此可用來延遲在 Q# 標準程式庫中或由使用者定義之任何作業的應用程式。</span><span class="sxs-lookup"><span data-stu-id="37c18-144">The @"microsoft.quantum.canon.delay" operation makes minimal assumptions about its input, and thus can be used to delay applications of either operations across the Q# standard library or as defined by users.</span></span>
    <!-- TODO: define bad example. -->

- <span data-ttu-id="37c18-145">✅會公開純決定性的傳統邏輯作為函式， **而不是** 作業。</span><span class="sxs-lookup"><span data-stu-id="37c18-145">✅ **DO** expose purely deterministic classical logic as   as functions rather than operations.</span></span>

  <span data-ttu-id="37c18-146">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-146">*Examples:*</span></span>
  - <span data-ttu-id="37c18-147">以決定性方式寫入其浮點數輸入的副程式可依決定性寫入，因此應該向使用者公開， `Squared : Double -> Double` 而不是做為作業 `Square : Double => Double` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-147">A subroutine which squares its floating-point input can be written deterministically, and so should be exposed to the user as `Squared : Double -> Double` rather than as an operation `Square : Double => Double`.</span></span> <span data-ttu-id="37c18-148">這可讓您在多個位置呼叫副程式 (例如：) 的其他函式內，並提供實用的優化資訊給編譯器，可能會影響效能和優化。</span><span class="sxs-lookup"><span data-stu-id="37c18-148">This allows for the subroutine to be called in more places (e.g.: inside of other functions), and provides useful optimization information to the compiler that can affect performance and optimizations.</span></span>
  - <span data-ttu-id="37c18-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` 和 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 確定性方面的保證不同，兩者在不同的情況下都很有用。</span><span class="sxs-lookup"><span data-stu-id="37c18-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` and `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` differ in the guarantees made with respect to   determinism; both are useful in different circumstances.</span></span>
  - <span data-ttu-id="37c18-150">轉換量子作業應用程式的 API 常式通常可以用決定性的方式來執行，因此可以用像這樣的功能   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-150">API routines that transform the application of quantum   operations can often be carried out in a deterministic     fashion and hence can be made available as functions such as   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.</span></span>

- <span data-ttu-id="37c18-151">✅**請視** 需要使用型別參數，將輸入類型一般化為每個函式和作業的合理程度。</span><span class="sxs-lookup"><span data-stu-id="37c18-151">✅ **DO** generalize the input type as much as reasonable for each   function and operation, using type parameters as needed.</span></span>

  <span data-ttu-id="37c18-152">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-152">*Examples:*</span></span>
  - <span data-ttu-id="37c18-153">`ApplyToEach` 具有類型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常見的應用程式的特定類型 `((Qubit => Unit), Qubit[]) => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-153">`ApplyToEach` has type `<'T>(('T => Unit), 'T[]) => Unit` rather than the specific type of its most common   application, `((Qubit => Unit), Qubit[]) => Unit`.</span></span>

> [!TIP]
> <span data-ttu-id="37c18-154">請務必預測未來的需求，但為您的使用者解決具體問題也很重要。</span><span class="sxs-lookup"><span data-stu-id="37c18-154">It is important to anticipate future needs, but it is also important to solve concrete problems for your users.</span></span>
> <span data-ttu-id="37c18-155">因此，請務必謹慎考慮並進行平衡，以避免開發 Api 「單純的情況」。</span><span class="sxs-lookup"><span data-stu-id="37c18-155">Acting on this key principle thus always requires careful consideration and balancing to avoid developing APIs "just in case."</span></span>

<span data-ttu-id="37c18-156">**主要原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可呼叫的目的。</span><span class="sxs-lookup"><span data-stu-id="37c18-156">**Key principle:** choose input and output types for functions and operations that are predictable, and that communicate the purpose of a callable.</span></span>

- <span data-ttu-id="37c18-157">✅**請** 使用元組類型，以邏輯方式將只視為重要的輸入和輸出群組在一起。</span><span class="sxs-lookup"><span data-stu-id="37c18-157">✅ **DO** use tuple types to logically group inputs and outputs that are only significant when considered together.</span></span> <span data-ttu-id="37c18-158">在這些情況下，請考慮使用使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="37c18-158">Consider using a user-defined type in these cases.</span></span>

  <span data-ttu-id="37c18-159">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-159">*Examples:*</span></span>
  - <span data-ttu-id="37c18-160">輸出另一個函式之本機最小值的函式可能需要以搜尋間隔作為輸入的界限，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。</span><span class="sxs-lookup"><span data-stu-id="37c18-160">A function to output the local minima of another function   may need to take bounds of a search interval as input, such   that `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` may be an appropriate signature.</span></span>
  - <span data-ttu-id="37c18-161">使用參數移位技術來評估機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。</span><span class="sxs-lookup"><span data-stu-id="37c18-161">An operation to estimate a derivative of a machine learning classifier using the parameter shift technique may need to take both the shifted and unshifted parameter vectors as inputs.</span></span> <span data-ttu-id="37c18-162">`(unshifted : Double[], shifted : Double[])`在此情況下，類似的輸入可能會很適合。</span><span class="sxs-lookup"><span data-stu-id="37c18-162">An input similar to `(unshifted : Double[], shifted : Double[])` may be appropriate in this case.</span></span>

- <span data-ttu-id="37c18-163">✅將輸入和輸出元集中的 **專案順序一致** 地跨不同的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="37c18-163">✅ **DO** order items in input and output tuples consistently   across different functions and operations.</span></span>

  <span data-ttu-id="37c18-164">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-164">*Examples:*</span></span>
  - <span data-ttu-id="37c18-165">如果考慮到兩個或各自採用旋轉角度和目標量子位做為輸入的兩個 or 函數或作業，請確定其在每個輸入元組中的排序方式都相同。</span><span class="sxs-lookup"><span data-stu-id="37c18-165">If considering two or functions or operations that each take a rotation angle and a target qubit as inputs, ensure that they are ordered the same in each input tuple.</span></span> <span data-ttu-id="37c18-166">也就是， `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 偏好 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 和 `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-166">That is, prefer `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` to `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="37c18-167">**主要原則：** 設計函數和作業，以便與 \# 部分應用程式等 Q 語言功能搭配運作。</span><span class="sxs-lookup"><span data-stu-id="37c18-167">**Key principle:** design functions and operations to work well with Q\# language features such as partial application.</span></span>

- <span data-ttu-id="37c18-168">✅在輸入元組中執行順序專案，讓最常套用的輸入先 (**也** 就是：，讓部分應用程式的運作方式類似于 currying) 。</span><span class="sxs-lookup"><span data-stu-id="37c18-168">✅ **DO** order items in input tuples such that the most commonly   applied inputs occur first (i.e.: so that partial application   acts similarly to currying).</span></span>

  <span data-ttu-id="37c18-169">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-169">*Examples:*</span></span>
  - <span data-ttu-id="37c18-170">以 `ApplyRotation` 浮點數和量子位作為輸入的作業，通常會先部分套用浮點數輸入，以便與預期類型輸入的作業搭配使用 `Qubit => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-170">An operation `ApplyRotation` that takes a floating-point number and a qubit as inputs may often be partially applied with the floating-point input first for use with operations that expect an input of type `Qubit => Unit`.</span></span> <span data-ttu-id="37c18-171">因此，簽章 `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span><span class="sxs-lookup"><span data-stu-id="37c18-171">Thus, a signature of `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span></span>
      <span data-ttu-id="37c18-172">在部分應用程式中最一致的運作方式。</span><span class="sxs-lookup"><span data-stu-id="37c18-172">would work most consistently with partial application.</span></span>
  - <span data-ttu-id="37c18-173">一般而言，本指引表示在輸入元組中的所有量子位之前，將所有傳統資料放在一起，但請使用良好的判斷，並檢查您的 API 在實務上的呼叫方式。</span><span class="sxs-lookup"><span data-stu-id="37c18-173">Typically, this guidance means placing all classical data   before all qubits in input tuples, but use good judgment and   examine how your API is called in practice.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="37c18-174">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="37c18-174">User-Defined Types</span></span>

<span data-ttu-id="37c18-175">**主要原則：** 使用使用者定義型別有助於讓 api 更具表達性且方便使用。</span><span class="sxs-lookup"><span data-stu-id="37c18-175">**Key principle:** use user-defined types to help make APIs more expressive and convenient to use.</span></span>

- <span data-ttu-id="37c18-176">✅**請** 加入新的使用者定義型別，以提供適用于 long 和/或複雜類型的實用速記。</span><span class="sxs-lookup"><span data-stu-id="37c18-176">✅ **DO** introduce new user-defined types to provide helpful   shorthand for long and/or complicated types.</span></span>

  <span data-ttu-id="37c18-177">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-177">*Examples:*</span></span>
  - <span data-ttu-id="37c18-178">在具有三個量子位陣列輸入的作業類型時，通常會將其視為輸入或傳回做為輸出，並提供如下的 UDT： `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span><span class="sxs-lookup"><span data-stu-id="37c18-178">In cases where an operation type with three qubit array inputs is commonly taken as an input or returned as an output, providing a UDT such as `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span></span>
      <span data-ttu-id="37c18-179">有助於提供實用的速記。</span><span class="sxs-lookup"><span data-stu-id="37c18-179">can help provide a useful shorthand.</span></span>

- <span data-ttu-id="37c18-180">✅**請** 建立新的使用者定義型別，以指出指定的基底類型應該只用于非常特殊的意義。</span><span class="sxs-lookup"><span data-stu-id="37c18-180">✅ **DO** introduce new user-defined types to indicate that a given   base type should only be used in a very particular sense.</span></span>

  <span data-ttu-id="37c18-181">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-181">*Examples:*</span></span>
  - <span data-ttu-id="37c18-182">應特別解讀為將傳統資料編碼成量子暫存器的作業，可能適合以使用者定義型別來標記 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-182">An operation that should be interpreted specifically as an   operation that encodes classical data into a quantum   register may be appropriate to label with a user-defined   type `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.</span></span>

- <span data-ttu-id="37c18-183">✅**請** 利用命名專案來引進新的使用者定義型別，以允許未來的擴充性 (例如：可能會在未來的) 中包含其他已命名專案的結果結構。</span><span class="sxs-lookup"><span data-stu-id="37c18-183">✅ **DO** introduce new user-defined types with named items that   allow for future extensibility (e.g.: a results structure that   may contain additional named items in the future).</span></span>

  <span data-ttu-id="37c18-184">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-184">*Examples:*</span></span>
  - <span data-ttu-id="37c18-185">當作業 `TrainModel` 公開大量的設定選項時，以新的 udt 公開這些選項，   `TrainingOptions` 並提供新的函式，   `DefaultTrainingOptions : Unit -> TrainingOptions` 可讓使用者在 TrainingOptions UDT 值中覆寫特定的已命名專案，同時仍然允許程式庫開發人員適當地加入新的 UDT 專案。</span><span class="sxs-lookup"><span data-stu-id="37c18-185">When an operation `TrainModel` exposes a large number of   configuration options, exposing these options as a new   `TrainingOptions` UDT and providing a new function   `DefaultTrainingOptions : Unit -> TrainingOptions` allows   users to override specific named items in TrainingOptions   UDT values while still allowing library developers to add   new UDT items as appropriate.</span></span>

- <span data-ttu-id="37c18-186">✅**請** 依照喜好設定為新的使用者定義類型宣告命名專案，要求使用者知道正確的元組解構。</span><span class="sxs-lookup"><span data-stu-id="37c18-186">✅ **DO** declare named items for new user-defined types in   preference to requiring users to know the correct tuple   deconstruction.</span></span>

  <span data-ttu-id="37c18-187">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-187">*Examples:*</span></span>
  - <span data-ttu-id="37c18-188">在其極值分解中表示覆數時，偏好   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 使用   `newtype ComplexPolar = (Double, Double)` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-188">When representing a complex number in its polar   decomposition, prefer   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` to   `newtype ComplexPolar = (Double, Double)`.</span></span>

<span data-ttu-id="37c18-189">**主要原則：** 使用使用者定義型別的方式可減少認知負載，而且不需要使用者學習其他概念和術語。</span><span class="sxs-lookup"><span data-stu-id="37c18-189">**Key principle:** use user-defined types in ways reduce  cognitive load and that don't require the user to learn additional concepts and nomenclature.</span></span>

- <span data-ttu-id="37c18-190">⛔️ **不** 會引進使用者定義型別，而使用者定義型別需要使用者經常使用解除包裝運算子 (`!`) ，或者通常需要多個解除包裝的層級。</span><span class="sxs-lookup"><span data-stu-id="37c18-190">⛔️ **DON'T** introduce user-defined types that require the user to make frequent use of the unwrap operator (`!`), or that commonly require multiple levels of unwrapping.</span></span> <span data-ttu-id="37c18-191">可能的緩和策略包括：</span><span class="sxs-lookup"><span data-stu-id="37c18-191">Possible mitigation strategies include:</span></span>

  - <span data-ttu-id="37c18-192">以單一專案公開使用者定義型別時，請考慮定義該專案的名稱。</span><span class="sxs-lookup"><span data-stu-id="37c18-192">When exposing a user-defined type with a single item, consider defining a name for that item.</span></span> <span data-ttu-id="37c18-193">例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 到的喜好設定 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-193">For instance, consider `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` in preference to `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.</span></span>

  - <span data-ttu-id="37c18-194">確保其他函式和作業可以直接接受「包裝」的 UDT 實例。</span><span class="sxs-lookup"><span data-stu-id="37c18-194">Ensuring that other functions and operations can accept   "wrapped" UDT instances directly.</span></span>

- <span data-ttu-id="37c18-195">⛔️ **不** 會引進新的使用者定義型別，這些類型會複製內建類型，而不會提供其他表達。</span><span class="sxs-lookup"><span data-stu-id="37c18-195">⛔️ **DON'T** introduce new user-defined types that duplicate   built-in types without providing additional expressiveness.</span></span>

  <span data-ttu-id="37c18-196">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-196">*Examples:*</span></span>
  - <span data-ttu-id="37c18-197">UDT `newtype QubitRegister = Qubit[]` 不提供任何其他表達 `Qubit[]` ，因此不會有明顯的優點，因此難以使用。</span><span class="sxs-lookup"><span data-stu-id="37c18-197">A UDT `newtype QubitRegister = Qubit[]` provides no   additional expressiveness over `Qubit[]`, and is thus harder   to use with no discernable benefit.</span></span>
  - <span data-ttu-id="37c18-198">UDT 會記載 `newtype LittleEndian = Qubit[]` 如何使用和解讀基礎暫存器，進而提供其基底類型的其他表達。</span><span class="sxs-lookup"><span data-stu-id="37c18-198">A UDT `newtype LittleEndian = Qubit[]` documents how the   underlying register is to be used and interpreted, and thus   provides additional expressiveness over its base type.</span></span>

- <span data-ttu-id="37c18-199">除非絕對必要，否則⛔️ **不** 會引進存取子函數;  在此情況下，強烈偏好命名專案。</span><span class="sxs-lookup"><span data-stu-id="37c18-199">⛔️ **DON'T** introduce accessor functions unless strictly required;   strongly prefer named items in this case.</span></span>

  <span data-ttu-id="37c18-200">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-200">*Examples:*</span></span>
  - <span data-ttu-id="37c18-201">引入 UDT 時 `newtype Complex = (Double, Double)` ，偏好將定義修改為，   `newtype Complex = (Real : Double, Imag : Double)` 以引入函式 `GetReal : Complex -> Double` 和   `GetImag : Complex -> Double` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-201">When introducing a UDT `newtype Complex = (Double, Double)`,   prefer modifying the definition to   `newtype Complex = (Real : Double, Imag : Double)` to introducing   functions `GetReal : Complex -> Double` and   `GetImag : Complex -> Double`.</span></span>

## <a name="namespaces-and-organization"></a><span data-ttu-id="37c18-202">命名空間和組織</span><span class="sxs-lookup"><span data-stu-id="37c18-202">Namespaces and Organization</span></span>

<span data-ttu-id="37c18-203">**主要原則：** 選擇可預測的命名空間名稱，並清楚地傳達每個命名空間中的函式、作業和使用者定義類型的用途。</span><span class="sxs-lookup"><span data-stu-id="37c18-203">**Key principle:** choose namespace names that are predictable and that clearly communicate the purpose of functions, operations, and user-defined types in each namespace.</span></span>

- <span data-ttu-id="37c18-204">✅將命名 **空間命名為** `Publisher.Product.DomainArea` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-204">✅ **DO** name namespaces as `Publisher.Product.DomainArea`.</span></span>

  <span data-ttu-id="37c18-205">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-205">*Examples:*</span></span>
  - <span data-ttu-id="37c18-206">由 Microsoft 發佈的函式、作業和 Udt 是量子開發工具組之量子模擬功能的一部分，會放在   `Microsoft.Quantum.Simulation` 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="37c18-206">Functions, operations, and UDTs published by Microsoft as a   part of the quantum simulation feature of the Quantum   Development Kit are placed in the   `Microsoft.Quantum.Simulation` namespace.</span></span>
  - <span data-ttu-id="37c18-207">`Microsoft.Quantum.Math` 代表 Microsoft 在與數學網域區域相關的量子開發工具組中所發佈的命名空間。</span><span class="sxs-lookup"><span data-stu-id="37c18-207">`Microsoft.Quantum.Math` represents a namespace   published by Microsoft as part of the Quantum Development   Kit pertaining to the mathematics domain area.</span></span>

- <span data-ttu-id="37c18-208">✅**請將用於** 特定功能的作業、函式和使用者定義類型，放入描述該功能的命名空間中，即使是在不同的問題網域中使用該功能。</span><span class="sxs-lookup"><span data-stu-id="37c18-208">✅ **DO** place operations, functions, and user-defined types used   for specific functionality into a namespace that describes that   functionality, even when that functionality is used across   different problem domains.</span></span>

  <span data-ttu-id="37c18-209">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-209">*Examples:*</span></span>
  - <span data-ttu-id="37c18-210">由 Microsoft 發佈作為量子開發工具組一部分的狀態準備 Api 將會放入   `Microsoft.Quantum.Preparation` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-210">State preparation APIs published by Microsoft as a part of   the Quantum Development Kit would be placed into   `Microsoft.Quantum.Preparation`.</span></span>
  - <span data-ttu-id="37c18-211">Microsoft 在量子開發工具組中發佈的量子模擬 Api 將會放入   `Microsoft.Quantum.Simulation` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-211">Quantum simulation APIs published by Microsoft as a part of the Quantum   Development Kit would be placed into   `Microsoft.Quantum.Simulation`.</span></span>

- <span data-ttu-id="37c18-212">✅**將作業**、函式和使用者定義型別只用于特定網域中，以表示其公用程式網域。</span><span class="sxs-lookup"><span data-stu-id="37c18-212">✅ **DO** place operations, functions, and user-defined types used only within specific domains into namespaces indicating their domain of utility.</span></span> <span data-ttu-id="37c18-213">如有需要，請使用子命名空間來指出每個特定領域命名空間內的焦點工作。</span><span class="sxs-lookup"><span data-stu-id="37c18-213">If needed, use subnamespaces to indicate focused tasks within each domain-specific namespace.</span></span>

  <span data-ttu-id="37c18-214">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-214">*Examples:*</span></span>
  - <span data-ttu-id="37c18-215">Microsoft 所發行的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets"   命名空間提供。</span><span class="sxs-lookup"><span data-stu-id="37c18-215">The quantum machine learning library published by Microsoft is largely   placed into the @"microsoft.quantum.machinelearning" namespace, but example   datasets are provided by the @"microsoft.quantum.machinelearning.datasets"   namespace.</span></span>
  - <span data-ttu-id="37c18-216">由 Microsoft 發佈作為量子開發工具組一部分的量子化學 Api 應該放入 `Microsoft.Quantum.Chemistry` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-216">Quantum chemistry APIs published by Microsoft as a part of the Quantum Development Kit should be placed into `Microsoft.Quantum.Chemistry`.</span></span> <span data-ttu-id="37c18-217">執行約旦--Wigner 分解的特定功能可能會放入 `Microsoft.Quantum.Chemistry.JordanWigner` ，因此量子化學網域區域的主要介面並不在意實行。</span><span class="sxs-lookup"><span data-stu-id="37c18-217">Functionality specific to implementing the Jordan--Wigner decomposition may be placed in `Microsoft.Quantum.Chemistry.JordanWigner`, so that the primary interface for the quantum chemistry domain area is not concerned with implementations.</span></span>

<span data-ttu-id="37c18-218">**主要原則：** 使用命名空間和存取修飾詞，以刻意刻意瞭解對使用者公開的 API 介面，以及隱藏與 Api 的執行和測試相關的內部詳細資料。</span><span class="sxs-lookup"><span data-stu-id="37c18-218">**Key principle:** Use namespaces and access modifiers together to be intentional about the API surface exposed to users, and to hide internal details related to implementation and testing of your APIs.</span></span>

- <span data-ttu-id="37c18-219">✅ 如果 **合理，請將將 api** 實作為所要執行之 api 的相同命名空間中的所有函式和作業放在同一命名空間中，但標示為「私用」或「內部」關鍵字，表示它們不是程式庫公用 API 介面的一部分。</span><span class="sxs-lookup"><span data-stu-id="37c18-219">✅ Whenever reasonable, **DO** place all functions and operations needed to implement an API into the same namespace as the API being implemented, but marked with the "private" or "internal" keywords to indicate that they are not part of the public API surface for a library.</span></span> <span data-ttu-id="37c18-220">使用以底線 (開頭的名稱 `_`) ，以視覺化方式區分私用和內部作業以及公用 callables 的函式。</span><span class="sxs-lookup"><span data-stu-id="37c18-220">Use a name beginning with an underscore (`_`) to visually distinguish private and internal operations and functions from public callables.</span></span>

  <span data-ttu-id="37c18-221">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-221">*Examples:*</span></span>
  - <span data-ttu-id="37c18-222">作業名稱 `_Features` 表示對指定的命名空間和元件而言是私用的函式，且應伴隨 `internal` 關鍵字。</span><span class="sxs-lookup"><span data-stu-id="37c18-222">The operation name `_Features` indicates a function that is   private to a given namespace and assembly, and should be   accompanied by either the `internal` keyword.</span></span>

- <span data-ttu-id="37c18-223">✅ 在罕見的情況下，需要一組廣泛的私用函式或作業以針對指定的命名 **空間執行 API 時，請** 將它們放在符合所要執行和結束之命名空間的新命名空間中 `.Private` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-223">✅ In the rare case that an extensive set of private functions or operations are needed to implement the API for a given namespace, **DO** place them in a new namespace matching the namespace being implemented and ending in `.Private`.</span></span>

- <span data-ttu-id="37c18-224">✅**請** 將所有單元測試放入符合受測命名空間的命名空間中，並在結尾 `.Tests` 。</span><span class="sxs-lookup"><span data-stu-id="37c18-224">✅ **DO** place all unit tests into namespaces matching the     namespace under test and ending in `.Tests`.</span></span>

## <a name="naming-conventions-and-vocabulary"></a><span data-ttu-id="37c18-225">命名慣例和詞彙</span><span class="sxs-lookup"><span data-stu-id="37c18-225">Naming Conventions and Vocabulary</span></span>

<span data-ttu-id="37c18-226">**主要原則：** 選擇在各種不同的物件範圍內清楚、可存取且可讀取的名稱和術語，包括量子新手和專家。</span><span class="sxs-lookup"><span data-stu-id="37c18-226">**Key principle:** Choose names and terminology that are clear, accessible, and readable across a diverse range of audiences, including both quantum novices and experts.</span></span>

- <span data-ttu-id="37c18-227">⛔️ **不** 使用歧視性或排他性行為識別碼名稱，也不使用 API 檔批註中的術語。</span><span class="sxs-lookup"><span data-stu-id="37c18-227">⛔️ **DON'T** use discriminatory or exclusionary identifier names,   nor terminology in API documentation comments.</span></span>

- <span data-ttu-id="37c18-228">✅**請使用 API** 檔批註來提供相關的內容、範例和參考，特別是針對更困難的概念。</span><span class="sxs-lookup"><span data-stu-id="37c18-228">✅ **DO** use API documentation comments to provide relevant   context, examples, and references, especially for more difficult   concepts.</span></span>

- <span data-ttu-id="37c18-229">⛔️ **不要** 使用不必要難理解的識別碼名稱，或需要大量量子演算法知識才能讀取的識別碼名稱。</span><span class="sxs-lookup"><span data-stu-id="37c18-229">⛔️ **DON'T** use identifier names that are unnecessarily esoteric,   or that require significant quantum algorithms knowledge to   read.</span></span>

  <span data-ttu-id="37c18-230">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-230">*Examples:*</span></span>
  - <span data-ttu-id="37c18-231">偏好「幅度放大反覆運算」至「格羅弗反復專案」。</span><span class="sxs-lookup"><span data-stu-id="37c18-231">Prefer "amplitude amplification iteration" to "Grover   iteration."</span></span>

- <span data-ttu-id="37c18-232">✅**請** 選擇作業和函式名稱，以明確地傳達可呼叫的預期效果，而不是其實作為。</span><span class="sxs-lookup"><span data-stu-id="37c18-232">✅ **DO** choose operations and function names that clearly communicate the intended effect of a callable, and not its implementation.</span></span> <span data-ttu-id="37c18-233">請注意，您可以和應該記載在 [API 檔批註](xref:microsoft.quantum.qsharp.comments#documentation-comments)中的執行。</span><span class="sxs-lookup"><span data-stu-id="37c18-233">Note that the implementation can and should be documented in [API documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments).</span></span>

  <span data-ttu-id="37c18-234">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-234">*Examples:*</span></span>
  - <span data-ttu-id="37c18-235">將「估計重迭」視為「Hadamard 測試」，因為後者會傳達前者的執行方式。</span><span class="sxs-lookup"><span data-stu-id="37c18-235">Prefer "estimate overlap" to "Hadamard test," as the latter   communicates how the former is implemented.</span></span>

- <span data-ttu-id="37c18-236">✅**請** 在所有 Q api 中以一致的方式使用單字 \# ：</span><span class="sxs-lookup"><span data-stu-id="37c18-236">✅ **DO** use words in a consistent fashion across all Q\# APIs:</span></span>

  - <span data-ttu-id="37c18-237">**動詞：**</span><span class="sxs-lookup"><span data-stu-id="37c18-237">**Verbs:**</span></span>

    - <span data-ttu-id="37c18-238">判斷 **提示：檢查** 目的電腦及其量子位狀態的相關假設是否保留，可能是使用 unphysical 資源。</span><span class="sxs-lookup"><span data-stu-id="37c18-238">**Assert**: Check that an assumption about the state of a target machine and its qubits holds, possibly by using unphysical resources.</span></span> <span data-ttu-id="37c18-239">使用這個動詞命令的作業應該一律安全地移除，而不會影響程式庫和可執行程式的功能。</span><span class="sxs-lookup"><span data-stu-id="37c18-239">Operations using this verb should always be safely removable without affecting the functionality of libraries and executable programs.</span></span> <span data-ttu-id="37c18-240">請注意，不同于事實，判斷提示通常會取決於外部狀態，例如量子位暫存器的狀態、執行環境等等。</span><span class="sxs-lookup"><span data-stu-id="37c18-240">Note that unlike facts, assertions may, in general, depend on external state, such as the state of a qubit register, the run environment or so forth.</span></span> <span data-ttu-id="37c18-241">因為外部狀態的相依性是一種副作用，所以判斷提示必須公開為作業，而不是函數。</span><span class="sxs-lookup"><span data-stu-id="37c18-241">As dependency on external state is a kind of side effect, assertions must be exposed as operations rather than functions.</span></span>

    - <span data-ttu-id="37c18-242">**估計**：使用一或多個可能重複的度量，從測量結果中估計傳統數量。</span><span class="sxs-lookup"><span data-stu-id="37c18-242">**Estimate**: Using one or more possibly repeated   measurements, estimate a classical quantity from   measurement results.</span></span>

      <span data-ttu-id="37c18-243">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-243">*Examples:*</span></span>
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - <span data-ttu-id="37c18-244">**準備**：將量子作業或作業順序套用至一或多個量子位，假設要在特定初始狀態下啟動 (通常是 $ \ket{00\cdots 0} $) ，導致這些量子位的狀態演進至所需的結束狀態。</span><span class="sxs-lookup"><span data-stu-id="37c18-244">**Prepare**: Apply a quantum operation or sequence of operations to one or more qubits assumed to start in a particular initial state (typically $\ket{00\cdots 0}$), causing the state of those qubits to evolve to a desired end state.</span></span> <span data-ttu-id="37c18-245">一般情況下，對指定啟動狀態以外的狀態採取動作， **可能會** 導致未定義的單一轉換，但是仍 **應** 保留作業及其 adjoint 「取消」並套用「無作業」。</span><span class="sxs-lookup"><span data-stu-id="37c18-245">In general, acting on states other than the given starting state **MAY** result in an undefined unitary transformation, but **SHOULD** still preserve that an operation and its adjoint "cancel out" and apply a no-op.</span></span>

      <span data-ttu-id="37c18-246">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-246">*Examples:*</span></span>
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - <span data-ttu-id="37c18-247">**Measure**：將量子作業或作業順序套用至一或多個量子位，然後再讀取傳統資料。</span><span class="sxs-lookup"><span data-stu-id="37c18-247">**Measure**: Apply a quantum operation or sequence of   operations to one or more qubits, reading classical data   back out.</span></span>

      <span data-ttu-id="37c18-248">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-248">*Examples:*</span></span>
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - <span data-ttu-id="37c18-249">**Apply**：將量子作業或作業順序套用至一或多個量子位，使這些量子位的狀態變更為一致的方式。</span><span class="sxs-lookup"><span data-stu-id="37c18-249">**Apply**: Apply a quantum operation or sequence of operations to one or more qubits, causing the state of those qubits to change in a coherent fashion.</span></span> <span data-ttu-id="37c18-250">此動詞命令是 Q 命名法中最常見的動詞命令 \# ， **不應** 在更明確相關的動詞時使用。</span><span class="sxs-lookup"><span data-stu-id="37c18-250">This verb is the most general verb in Q\# nomenclature, and **SHOULD NOT BE** used when a more specific verb is more directly relevant.</span></span>

  - <span data-ttu-id="37c18-251">**名詞**：</span><span class="sxs-lookup"><span data-stu-id="37c18-251">**Nouns**:</span></span>

    - <span data-ttu-id="37c18-252">**事實**：只取決於其輸入的布林條件，而不是目的電腦的狀態、其環境或電腦量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="37c18-252">**Fact**: A Boolean condition which depends only on its inputs and not on the state of a target machine, its environment, or the state of the machine's qubits.</span></span> <span data-ttu-id="37c18-253">相較于判斷提示，事實只會對提供給該事實的 *值* 有所區分。</span><span class="sxs-lookup"><span data-stu-id="37c18-253">By contrast with an assertion, a fact is only sensitive to the *values* provided to that fact.</span></span> <span data-ttu-id="37c18-254">例如：</span><span class="sxs-lookup"><span data-stu-id="37c18-254">For example:</span></span>

      <span data-ttu-id="37c18-255">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-255">*Examples:*</span></span>
      - <span data-ttu-id="37c18-256">@"microsoft.quantum.diagnostics.equalityfacti"：表示兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或與任何其他程式狀態無關。</span><span class="sxs-lookup"><span data-stu-id="37c18-256">@"microsoft.quantum.diagnostics.equalityfacti": represents an equality fact about two integer inputs; either the integers provided as input are equal to each other, or they are not, independent of any other program state.</span></span>

    - <span data-ttu-id="37c18-257">**選項：** 包含數個命名專案的 UDT，這些專案可作為函式或作業的「選擇性引數」。</span><span class="sxs-lookup"><span data-stu-id="37c18-257">**Options:** A UDT containing several named items that can act as "optional arguments" to a function or operation.</span></span> <span data-ttu-id="37c18-258">例如：</span><span class="sxs-lookup"><span data-stu-id="37c18-258">For example:</span></span>

      <span data-ttu-id="37c18-259">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-259">*Examples:*</span></span>
      - <span data-ttu-id="37c18-260">@"microsoft.quantum.machinelearning.trainingoptions"UDT 包含適用于學習速率、迷你批次大小和其他可設定之 ML 訓練參數的命名專案。</span><span class="sxs-lookup"><span data-stu-id="37c18-260">The @"microsoft.quantum.machinelearning.trainingoptions" UDT includes named items for learning rate, minibatch size, and other configurable parameters for ML training.</span></span>

  - <span data-ttu-id="37c18-261">**形容詞**：</span><span class="sxs-lookup"><span data-stu-id="37c18-261">**Adjectives**:</span></span>

    - <span data-ttu-id="37c18-262">⛔️ **New**： **不應** 使用這項形容詞，以避免在許多程式設計語言中將其使用方式與動詞混淆 (例如： c + +、c #、JAVA、TypeScript、PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="37c18-262">⛔️ **New**: This adjective **SHOULD NOT** be used, as to avoid confusion   with its usage as a verb in many   programming languages (e.g.: C++, C#, Java, TypeScript, PowerShell).</span></span>

  - <span data-ttu-id="37c18-263">**介係詞：** 在某些情況下，介係詞可用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。</span><span class="sxs-lookup"><span data-stu-id="37c18-263">**Prepositions:** In some cases, prepositions can be used to further disambiguate or clarify the roles of nouns and verbs in function and operation names.</span></span> <span data-ttu-id="37c18-264">不過，請務必謹慎且一致地執行此動作。</span><span class="sxs-lookup"><span data-stu-id="37c18-264">Care should be taken to do so sparingly and consistently, however.</span></span>

    - <span data-ttu-id="37c18-265">**如下：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示 **為** *X* ，而不是其原始標記法。</span><span class="sxs-lookup"><span data-stu-id="37c18-265">**As:** Represents that a function's input and output represent the same information, but that the output represents that information **as** an *X* instead of its original representation.</span></span> <span data-ttu-id="37c18-266">這特別適用于型別轉換函數。</span><span class="sxs-lookup"><span data-stu-id="37c18-266">This is especially common for type conversion functions.</span></span>

      <span data-ttu-id="37c18-267">*範例：*</span><span class="sxs-lookup"><span data-stu-id="37c18-267">*Examples:*</span></span>
      - <span data-ttu-id="37c18-268">`IntAsDouble(2)` 指出輸入 (`2`) 和輸出 (`2.0`) 表示品質相同的資訊，但使用不同的 Q \# 資料類型來進行這項操作。</span><span class="sxs-lookup"><span data-stu-id="37c18-268">`IntAsDouble(2)` indicates that both the input (`2`) and the output (`2.0`)   represent qualitatively the same information, but using   different Q\# data types to do so.</span></span>

    - <span data-ttu-id="37c18-269">**來源：** 為了確保一致性，此介係詞   **不應該** 用來指出類型轉換函式或任何其他 **適合的情況** 。</span><span class="sxs-lookup"><span data-stu-id="37c18-269">**From:** To ensure consistency, this preposition   **SHOULD NOT** be used to indicate type conversion   functions or any other case where **As** is appropriate.</span></span>

    - <span data-ttu-id="37c18-270">⛔️ **為：** **不應** 使用這個介係詞，以避免在許多程式設計語言中，將其使用方式與動詞混淆。</span><span class="sxs-lookup"><span data-stu-id="37c18-270">⛔️ **To:** This preposition **SHOULD NOT** be used, as to   avoid confusion with its usage as a verb in many   programming languages.</span></span>
