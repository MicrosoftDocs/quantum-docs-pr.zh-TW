---
title: '問 # API 設計原則'
description: '問 # API 設計原則'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024197"
---
# <a name="q-api-design-principles"></a><span data-ttu-id="8180d-103">問 # API 設計原則</span><span class="sxs-lookup"><span data-stu-id="8180d-103">Q# API Design Principles</span></span>

## <a name="introduction"></a><span data-ttu-id="8180d-104">簡介</span><span class="sxs-lookup"><span data-stu-id="8180d-104">Introduction</span></span>

<span data-ttu-id="8180d-105">問 # 是一種語言和平臺，可讓使用者撰寫、執行、瞭解及探索量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="8180d-105">As a language and as a platform, Q# empowers users to write, run, understand, and explore quantum applications.</span></span>
<span data-ttu-id="8180d-106">為了加強使用者的能力，當我們設計問 # 程式庫時，我們會遵循一組 API 設計原則來引導我們的設計，並協助我們為「量子開發」社區提供可用的程式庫。</span><span class="sxs-lookup"><span data-stu-id="8180d-106">In order to empower users, when we design Q# libraries, we follow a set of API design principles to guide our designs and to help us make usable libraries for the the quantum development community.</span></span>
<span data-ttu-id="8180d-107">本文將列出這些原則，並提供範例，以協助引導您在設計問 # Api 時如何套用它們。</span><span class="sxs-lookup"><span data-stu-id="8180d-107">This article lists these principles, and gives examples to help guide how to apply them when designing Q# APIs.</span></span>

> [!TIP]
> <span data-ttu-id="8180d-108">這是相當詳細的檔，旨在協助引導媒體櫃開發和深入的程式庫投稿。</span><span class="sxs-lookup"><span data-stu-id="8180d-108">This is a fairly detailed document that's intended to help guide library development and in-depth library contributions.</span></span>
> <span data-ttu-id="8180d-109">如果您是在 Q # 中撰寫自己的程式庫，或在[問 #](https://github.com/microsoft/QuantumLibraries)程式庫中提供較大的功能，您可能會發現它最有用。</span><span class="sxs-lookup"><span data-stu-id="8180d-109">You'll probably find it most useful if you're writing your own libraries in Q#, or if you're contributing larger features to the [Q# libraries repository](https://github.com/microsoft/QuantumLibraries).</span></span>
>
> <span data-ttu-id="8180d-110">另一方面，如果您想要瞭解如何更廣泛地參與「量子開發工具組」，建議您從「[貢獻指南](xref:microsoft.quantum.contributing)」開始。</span><span class="sxs-lookup"><span data-stu-id="8180d-110">On the other hand, if you're looking to learn how to contribute to the Quantum Development Kit more generally, we suggest starting with the [contribution guide](xref:microsoft.quantum.contributing).</span></span>
> <span data-ttu-id="8180d-111">如果您要尋找有關我們建議如何格式化問 # 程式碼的一般資訊，您可能會想要查看[樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="8180d-111">If you're looking for more general information about how we recommend formatting your Q# code, you may be interested in checking out the [style guide](xref:microsoft.quantum.contributing.style).</span></span>

## <a name="general-principles"></a><span data-ttu-id="8180d-112">一般原則</span><span class="sxs-lookup"><span data-stu-id="8180d-112">General Principles</span></span>

<span data-ttu-id="8180d-113">**主要原則：** 公開將焦點放在量子應用程式的 Api。</span><span class="sxs-lookup"><span data-stu-id="8180d-113">**Key principle:** Expose APIs that places the focus on quantum applications.</span></span>

- <span data-ttu-id="8180d-114">✅**請**選擇反映演算法和應用程式之高階結構的作業和函式名稱。</span><span class="sxs-lookup"><span data-stu-id="8180d-114">✅ **DO** choose operation and function names that reflect the   high-level structure of algorithms and applications.</span></span>
- <span data-ttu-id="8180d-115">⛔️**不**會公開主要著重于低層級執行詳細資料的 api。</span><span class="sxs-lookup"><span data-stu-id="8180d-115">⛔️ **DON'T** expose APIs that focus primarily on low-level   implementation details.</span></span>

<span data-ttu-id="8180d-116">**主要原則：** 使用範例使用案例來啟動每個 API 設計，以確保 Api 可直覺使用。</span><span class="sxs-lookup"><span data-stu-id="8180d-116">**Key principle:** Start each API design with sample use cases to ensure that APIs are intuitive to use.</span></span>

- <span data-ttu-id="8180d-117">✅**確實**確保公用 API 的每個元件都有對應的使用案例，而不是嘗試針對從開頭進行的所有可能用法進行設計。</span><span class="sxs-lookup"><span data-stu-id="8180d-117">✅ **DO** ensure that each component of a public API has a corresponding use case, rather than trying to design for all possible uses from the start.</span></span>
    <span data-ttu-id="8180d-118">以不同的方式進行，請不要引進公用 Api，以免其有用，但請確定 API 的每個部分都有*具體*的範例，其中會很有用。</span><span class="sxs-lookup"><span data-stu-id="8180d-118">Put differently, don't introduce public APIs in case they are useful, but make sure that each part of an API has a *concrete* example in which it will be useful.</span></span>

  <span data-ttu-id="8180d-119">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-119">*Examples:*</span></span>
  - <span data-ttu-id="8180d-120">@"microsoft.quantum.canon.applytoeachca" 可用來做為 `ApplyToEachCA(H, _)`，以統一重迭狀態準備暫存器，這是許多配量演算法中的一般工作。</span><span class="sxs-lookup"><span data-stu-id="8180d-120">@"microsoft.quantum.canon.applytoeachca" can be used as `ApplyToEachCA(H, _)` to prepare registers in a uniform superposition state, a common task in many quantum algorithms.</span></span> <span data-ttu-id="8180d-121">相同的作業也可以用於準備、數值和 oracle 型演算法中的許多其他工作。</span><span class="sxs-lookup"><span data-stu-id="8180d-121">The same operation can also be used for many other tasks in preparation, numerics, and oracle-based algorithms.</span></span>

- <span data-ttu-id="8180d-122">✅**進行**靈感討論會和研討會新的 API 設計，以再次檢查它們是否直覺，並符合建議的使用案例。</span><span class="sxs-lookup"><span data-stu-id="8180d-122">✅ **DO** brainstorm and workshop new API designs to double-check   that they are intuitive and meet proposed use cases.</span></span>

  <span data-ttu-id="8180d-123">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-123">*Examples:*</span></span>
  - <span data-ttu-id="8180d-124">檢查目前的 Q\# 程式碼，以瞭解新的 API 設計如何簡化並闡明現有的實作為。</span><span class="sxs-lookup"><span data-stu-id="8180d-124">Inspect current Q\# code to see how new API designs could   simplify and clarify existing implementations.</span></span>
  - <span data-ttu-id="8180d-125">使用主要物件的代表來審查提議的 API 設計。</span><span class="sxs-lookup"><span data-stu-id="8180d-125">Review proposed API designs with representatives of primary   audiences.</span></span>

<span data-ttu-id="8180d-126">**主要原則：** 設計 Api 以支援和鼓勵可讀取的程式碼。</span><span class="sxs-lookup"><span data-stu-id="8180d-126">**Key principle:** Design APIs to support and encourage readable code.</span></span>

- <span data-ttu-id="8180d-127">✅**確實**確保網域專家和非專家都能讀取程式碼。</span><span class="sxs-lookup"><span data-stu-id="8180d-127">✅ **DO** ensure that code is readable by domain experts and   non-experts alike.</span></span>
- <span data-ttu-id="8180d-128">✅**會將焦點**放在高階演算法中每個作業和函式的效果，並使用檔來深入瞭解適用的執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8180d-128">✅ **DO** place the focus on the effects of each operation and   function within the high-level algorithm, using documentation to   delve into implementation details as appropriate.</span></span>
- <span data-ttu-id="8180d-129">✅**確實**遵循一般的[Q\# 樣式指南](xref:microsoft.quantum.contributing.style)（如果適用）。</span><span class="sxs-lookup"><span data-stu-id="8180d-129">✅ **DO** follow the common [Q\# style guide](xref:microsoft.quantum.contributing.style) whenever applicable.</span></span>

<span data-ttu-id="8180d-130">**主要原則：** 將 Api 設計為穩定的，並提供向前相容性。</span><span class="sxs-lookup"><span data-stu-id="8180d-130">**Key principle:** Design APIs to be stable and to provide forward compatibility.</span></span>

- <span data-ttu-id="8180d-131">✅**在**需要中斷性變更時，可以正常地取代舊的 api。</span><span class="sxs-lookup"><span data-stu-id="8180d-131">✅ **DO** deprecate old APIs gracefully when breaking changes are   required.</span></span>

- <span data-ttu-id="8180d-132">✅ 提供「填充碼」作業和函式，**可讓現有**的使用者程式碼在淘汰期間正常運作。</span><span class="sxs-lookup"><span data-stu-id="8180d-132">✅ **DO** provide "shim" operations and functions that allow   existing user code to operate correctly during deprecation.</span></span>

  <span data-ttu-id="8180d-133">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-133">*Examples:*</span></span>
  - <span data-ttu-id="8180d-134">將名為 `EstimateExpectation` 的作業重新命名為 `EstimateAverage`時，會引進名為 `EstimateExpectation` 的新作業，此作業會在其新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。</span><span class="sxs-lookup"><span data-stu-id="8180d-134">When renaming an operation called `EstimateExpectation` to   `EstimateAverage`, introduce a new operation called   `EstimateExpectation` that calls the original operation at   its new name, so that existing code can continue to work   correctly.</span></span>

- <span data-ttu-id="8180d-135">✅**確實**使用 @"microsoft.quantum.core.deprecated" 屬性來與使用者通訊棄用功能。</span><span class="sxs-lookup"><span data-stu-id="8180d-135">✅ **DO** use the @"microsoft.quantum.core.deprecated" attribute to communicate deprecations to the user.</span></span>

- <span data-ttu-id="8180d-136">✅ 重新命名作業或函式時 **，請**提供新的名稱做為 `@Deprecated`的字串輸入。</span><span class="sxs-lookup"><span data-stu-id="8180d-136">✅ When renaming an operation or function, **DO** provide the new   name as a string input to `@Deprecated`.</span></span>

- <span data-ttu-id="8180d-137">⛔️在預覽版本中，**請勿**移除至少六個月後的現有函式或作業，或至少兩年的支援版本。</span><span class="sxs-lookup"><span data-stu-id="8180d-137">⛔️ **DON'T** remove existing functions or operations without a   deprecation period of at least six months for preview releases,   or at least two years for supported releases.</span></span>

## <a name="functions-and-operations"></a><span data-ttu-id="8180d-138">函數和作業</span><span class="sxs-lookup"><span data-stu-id="8180d-138">Functions and Operations</span></span>

<span data-ttu-id="8180d-139">**主要原則：** 確保每個函式和作業在 API 內都有一個定義完善的目的。</span><span class="sxs-lookup"><span data-stu-id="8180d-139">**Key principle:** ensure that every function and operation has a single well-defined purpose within the API.</span></span>

- <span data-ttu-id="8180d-140">⛔️**不**會公開執行多個不相關工作的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="8180d-140">⛔️ **DON'T** expose functions and operations that perform multiple   unrelated tasks.</span></span>

<span data-ttu-id="8180d-141">**主要原則：** 盡可能將函式和作業設計為可重複使用，並預期未來的需求。</span><span class="sxs-lookup"><span data-stu-id="8180d-141">**Key principle:** design functions and operations to be as reusable as possible, and to anticipate future needs.</span></span>

- <span data-ttu-id="8180d-142">✅**執行**設計函式和作業，以便在相同的 API 和先前現有的程式庫中，妥善地與其他函式和作業一起撰寫。</span><span class="sxs-lookup"><span data-stu-id="8180d-142">✅ **DO** design functions and operations to compose well with other   functions and operations, both in the same API and in previously   existing libraries.</span></span>

  <span data-ttu-id="8180d-143">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-143">*Examples:*</span></span>
  - <span data-ttu-id="8180d-144">@"microsoft.quantum.canon.delay" 作業會對其輸入做出最低的假設，因此可以用來延遲在 Q # 標準程式庫或由使用者定義的任一作業的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8180d-144">The @"microsoft.quantum.canon.delay" operation makes minimal assumptions about its input, and thus can be used to delay applications of either operations across the Q# standard library or as defined by users.</span></span>
    <!-- TODO: define bad example. -->

- <span data-ttu-id="8180d-145">✅**確實**會將純粹具決定性的傳統邏輯公開為函式，而不是作業。</span><span class="sxs-lookup"><span data-stu-id="8180d-145">✅ **DO** expose purely deterministic classical logic as   as functions rather than operations.</span></span>

  <span data-ttu-id="8180d-146">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-146">*Examples:*</span></span>
  - <span data-ttu-id="8180d-147">會以決定性的方式寫入其浮點輸入的副程式，因此應該向使用者公開為 `Squared : Double -> Double`，而不是 `Square : Double => Double`作業。</span><span class="sxs-lookup"><span data-stu-id="8180d-147">A subroutine which squares its floating-point input can be written deterministically, and so should be exposed to the user as `Squared : Double -> Double` rather than as an operation `Square : Double => Double`.</span></span> <span data-ttu-id="8180d-148">這可讓您在多個位置呼叫副程式（例如：在其他函式中），並提供實用的優化資訊給編譯器，這可能會影響效能和優化。</span><span class="sxs-lookup"><span data-stu-id="8180d-148">This allows for the subroutine to be called in more places (e.g.: inside of other functions), and provides useful optimization information to the compiler that can affect performance and optimizations.</span></span>
  - <span data-ttu-id="8180d-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` 和 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 在保證方面有不同的確定性;兩者在不同的情況下都很有用。</span><span class="sxs-lookup"><span data-stu-id="8180d-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` and `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` differ in the guarantees made with respect to   determinism; both are useful in different circumstances.</span></span>
  - <span data-ttu-id="8180d-150">轉換量子作業之應用程式的 API 常式，通常會以決定性的方式執行，因此可做為 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`之類的函式使用。</span><span class="sxs-lookup"><span data-stu-id="8180d-150">API routines that transform the application of quantum   operations can often be carried out in a deterministic     fashion and hence can be made available as functions such as   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.</span></span>

- <span data-ttu-id="8180d-151">✅**會**視需要使用型別參數，將輸入型別一般化為每個函式和作業的合理程度。</span><span class="sxs-lookup"><span data-stu-id="8180d-151">✅ **DO** generalize the input type as much as reasonable for each   function and operation, using type parameters as needed.</span></span>

  <span data-ttu-id="8180d-152">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-152">*Examples:*</span></span>
  - <span data-ttu-id="8180d-153">`ApplyToEach` 具有類型 `<'T>(('T => Unit), 'T[]) => Unit`，而不是其最常見應用程式的特定類型，`((Qubit => Unit), Qubit[]) => Unit`。</span><span class="sxs-lookup"><span data-stu-id="8180d-153">`ApplyToEach` has type `<'T>(('T => Unit), 'T[]) => Unit` rather than the specific type of its most common   application, `((Qubit => Unit), Qubit[]) => Unit`.</span></span>

> [!TIP]
> <span data-ttu-id="8180d-154">請務必預測未來的需求，但針對您的使用者解決具體的問題也很重要。</span><span class="sxs-lookup"><span data-stu-id="8180d-154">It is important to anticipate future needs, but it is also important to solve concrete problems for your users.</span></span>
> <span data-ttu-id="8180d-155">因此，基於此主要原則的作用，一律需要謹慎考慮並進行平衡，以避免開發 Api 「以防萬一」。</span><span class="sxs-lookup"><span data-stu-id="8180d-155">Acting on this key principle thus always requires careful consideration and balancing to avoid developing APIs "just in case."</span></span>

<span data-ttu-id="8180d-156">索引**鍵原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可以呼叫的目的。</span><span class="sxs-lookup"><span data-stu-id="8180d-156">**Key principle:** choose input and output types for functions and operations that are predictable, and that communicate the purpose of a callable.</span></span>

- <span data-ttu-id="8180d-157">✅**確實**會使用元組類型，以邏輯方式將輸入和輸出分組，而這些只會在同時被視為重要。</span><span class="sxs-lookup"><span data-stu-id="8180d-157">✅ **DO** use tuple types to logically group inputs and outputs that are only significant when considered together.</span></span> <span data-ttu-id="8180d-158">在這些情況下，請考慮使用使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="8180d-158">Consider using a user-defined type in these cases.</span></span>

  <span data-ttu-id="8180d-159">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-159">*Examples:*</span></span>
  - <span data-ttu-id="8180d-160">輸出另一個函式之本機 minima 的函式可能需要將搜尋間隔的界限當做輸入，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。</span><span class="sxs-lookup"><span data-stu-id="8180d-160">A function to output the local minima of another function   may need to take bounds of a search interval as input, such   that `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` may be an appropriate signature.</span></span>
  - <span data-ttu-id="8180d-161">使用參數移位技術來估計機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。</span><span class="sxs-lookup"><span data-stu-id="8180d-161">An operation to estimate a derivative of a machine learning classifier using the parameter shift technique may need to take both the shifted and unshifted parameter vectors as inputs.</span></span> <span data-ttu-id="8180d-162">在此情況下，類似于 `(unshifted : Double[], shifted : Double[])` 的輸入可能會很適當。</span><span class="sxs-lookup"><span data-stu-id="8180d-162">An input similar to `(unshifted : Double[], shifted : Double[])` may be appropriate in this case.</span></span>

- <span data-ttu-id="8180d-163">✅**會**在不同的函式和作業之間一致地排序輸入和輸出元組中的專案。</span><span class="sxs-lookup"><span data-stu-id="8180d-163">✅ **DO** order items in input and output tuples consistently   across different functions and operations.</span></span>

  <span data-ttu-id="8180d-164">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-164">*Examples:*</span></span>
  - <span data-ttu-id="8180d-165">如果考慮兩個或函式或作業，其中每個都採用旋轉角度和目標 qubit 做為輸入，請確定在每個輸入元組中，都有相同的排序方式。</span><span class="sxs-lookup"><span data-stu-id="8180d-165">If considering two or functions or operations that each take a rotation angle and a target qubit as inputs, ensure that they are ordered the same in each input tuple.</span></span> <span data-ttu-id="8180d-166">也就是，偏好 `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`，並 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` 和 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="8180d-166">That is, prefer `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` to `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="8180d-167">**主要原則：** 設計函式和作業來與 Q\# 語言功能（例如部分應用程式）搭配運作。</span><span class="sxs-lookup"><span data-stu-id="8180d-167">**Key principle:** design functions and operations to work well with Q\# language features such as partial application.</span></span>

- <span data-ttu-id="8180d-168">✅**執行**輸入元組中的專案順序，使最常套用的輸入發生（也就是：讓部分應用程式的行為類似于 currying）。</span><span class="sxs-lookup"><span data-stu-id="8180d-168">✅ **DO** order items in input tuples such that the most commonly   applied inputs occur first (i.e.: so that partial application   acts similarly to currying).</span></span>

  <span data-ttu-id="8180d-169">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-169">*Examples:*</span></span>
  - <span data-ttu-id="8180d-170">使用浮點數和 qubit 做為輸入的作業 `ApplyRotation` 通常會先部分套用至浮點輸入，以搭配預期型別為 `Qubit => Unit`的輸入。</span><span class="sxs-lookup"><span data-stu-id="8180d-170">An operation `ApplyRotation` that takes a floating-point number and a qubit as inputs may often be partially applied with the floating-point input first for use with operations that expect an input of type `Qubit => Unit`.</span></span> <span data-ttu-id="8180d-171">因此，`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 的簽章</span><span class="sxs-lookup"><span data-stu-id="8180d-171">Thus, a signature of `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span></span>
      <span data-ttu-id="8180d-172">會與部分應用程式一致地搭配使用。</span><span class="sxs-lookup"><span data-stu-id="8180d-172">would work most consistently with partial application.</span></span>
  - <span data-ttu-id="8180d-173">一般而言，本指南表示將所有傳統資料放在輸入元組的所有 qubits 之前，但請使用良好的判斷，並檢查您的 API 在實務中的呼叫方式。</span><span class="sxs-lookup"><span data-stu-id="8180d-173">Typically, this guidance means placing all classical data   before all qubits in input tuples, but use good judgment and   examine how your API is called in practice.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="8180d-174">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="8180d-174">User-Defined Types</span></span>

<span data-ttu-id="8180d-175">**主要原則：** 使用使用者定義型別，協助讓 api 更具表達性且方便使用。</span><span class="sxs-lookup"><span data-stu-id="8180d-175">**Key principle:** use user-defined types to help make APIs more expressive and convenient to use.</span></span>

- <span data-ttu-id="8180d-176">✅**會**引進新的使用者定義型別，為長和/或複雜型別提供有用的速記。</span><span class="sxs-lookup"><span data-stu-id="8180d-176">✅ **DO** introduce new user-defined types to provide helpful   shorthand for long and/or complicated types.</span></span>

  <span data-ttu-id="8180d-177">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-177">*Examples:*</span></span>
  - <span data-ttu-id="8180d-178">如果具有三個 qubit 陣列輸入的作業類型通常會做為輸入或當做輸出傳回，則會提供 UDT，例如 `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span><span class="sxs-lookup"><span data-stu-id="8180d-178">In cases where an operation type with three qubit array inputs is commonly taken as an input or returned as an output, providing a UDT such as `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span></span>
      <span data-ttu-id="8180d-179">有助於提供有用的速記。</span><span class="sxs-lookup"><span data-stu-id="8180d-179">can help provide a useful shorthand.</span></span>

- <span data-ttu-id="8180d-180">✅**會**引進新的使用者定義型別，以指出給定的基底型別應該僅用於非常特殊的意義。</span><span class="sxs-lookup"><span data-stu-id="8180d-180">✅ **DO** introduce new user-defined types to indicate that a given   base type should only be used in a very particular sense.</span></span>

  <span data-ttu-id="8180d-181">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-181">*Examples:*</span></span>
  - <span data-ttu-id="8180d-182">應該特別解讀為將傳統資料編碼成量子暫存器的作業，可能適用于具有使用者定義類型 `newtype InputEncoder = (Apply : (Qubit[] => Unit))`的標籤。</span><span class="sxs-lookup"><span data-stu-id="8180d-182">An operation that should be interpreted specifically as an   operation that encodes classical data into a quantum   register may be appropriate to label with a user-defined   type `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.</span></span>

- <span data-ttu-id="8180d-183">✅**確實**引進了新的使用者定義型別，其中包含允許未來擴充性的命名專案（例如：未來可能會包含其他命名專案的結果結構）。</span><span class="sxs-lookup"><span data-stu-id="8180d-183">✅ **DO** introduce new user-defined types with named items that   allow for future extensibility (e.g.: a results structure that   may contain additional named items in the future).</span></span>

  <span data-ttu-id="8180d-184">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-184">*Examples:*</span></span>
  - <span data-ttu-id="8180d-185">當作業 `TrainModel` 公開大量的設定選項時，會將這些選項公開為新的 `TrainingOptions` UDT，並提供新的函式 `DefaultTrainingOptions : Unit -> TrainingOptions` 讓使用者能夠覆寫 TrainingOptions UDT 值中的特定已命名專案，同時仍然允許程式庫開發人員視需要加入新的 UDT 專案。</span><span class="sxs-lookup"><span data-stu-id="8180d-185">When an operation `TrainModel` exposes a large number of   configuration options, exposing these options as a new   `TrainingOptions` UDT and providing a new function   `DefaultTrainingOptions : Unit -> TrainingOptions` allows   users to override specific named items in TrainingOptions   UDT values while still allowing library developers to add   new UDT items as appropriate.</span></span>

- <span data-ttu-id="8180d-186">✅**請**在喜好設定中為新的使用者定義型別宣告命名專案，以要求使用者知道正確的元組解構。</span><span class="sxs-lookup"><span data-stu-id="8180d-186">✅ **DO** declare named items for new user-defined types in   preference to requiring users to know the correct tuple   deconstruction.</span></span>

  <span data-ttu-id="8180d-187">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-187">*Examples:*</span></span>
  - <span data-ttu-id="8180d-188">當代表其極座標分解中的複數時，偏好 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 來 `newtype ComplexPolar = (Double, Double)`。</span><span class="sxs-lookup"><span data-stu-id="8180d-188">When representing a complex number in its polar   decomposition, prefer   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` to   `newtype ComplexPolar = (Double, Double)`.</span></span>

<span data-ttu-id="8180d-189">**主要原則：** 使用使用者定義型別，方法是減少認知負載，而不需要使用者學習其他概念和命名法。</span><span class="sxs-lookup"><span data-stu-id="8180d-189">**Key principle:** use user-defined types in ways reduce  cognitive load and that don't require the user to learn additional concepts and nomenclature.</span></span>

- <span data-ttu-id="8180d-190">⛔️**不**會引進使用者定義的型別，要求使用者經常使用解除包裝運算子（`!`），或通常需要多個解除包裝的層級。</span><span class="sxs-lookup"><span data-stu-id="8180d-190">⛔️ **DON'T** introduce user-defined types that require the user to make frequent use of the unwrap operator (`!`), or that commonly require multiple levels of unwrapping.</span></span> <span data-ttu-id="8180d-191">可能的緩和策略包括：</span><span class="sxs-lookup"><span data-stu-id="8180d-191">Possible mitigation strategies include:</span></span>

  - <span data-ttu-id="8180d-192">以單一專案公開使用者定義的型別時，請考慮定義該專案的名稱。</span><span class="sxs-lookup"><span data-stu-id="8180d-192">When exposing a user-defined type with a single item, consider defining a name for that item.</span></span> <span data-ttu-id="8180d-193">例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="8180d-193">For instance, consider `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` in preference to `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.</span></span>

  - <span data-ttu-id="8180d-194">確保其他函數和作業可以直接接受「包裝的」 UDT 實例。</span><span class="sxs-lookup"><span data-stu-id="8180d-194">Ensuring that other functions and operations can accept   "wrapped" UDT instances directly.</span></span>

- <span data-ttu-id="8180d-195">⛔️**不**會導入重複內建類型的新使用者定義類型，而不會提供其他表達。</span><span class="sxs-lookup"><span data-stu-id="8180d-195">⛔️ **DON'T** introduce new user-defined types that duplicate   built-in types without providing additional expressiveness.</span></span>

  <span data-ttu-id="8180d-196">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-196">*Examples:*</span></span>
  - <span data-ttu-id="8180d-197">UDT `newtype QubitRegister = Qubit[]` 不會針對 `Qubit[]`提供任何額外的表達，因此更難使用，而不會有明顯的好處。</span><span class="sxs-lookup"><span data-stu-id="8180d-197">A UDT `newtype QubitRegister = Qubit[]` provides no   additional expressiveness over `Qubit[]`, and is thus harder   to use with no discernable benefit.</span></span>
  - <span data-ttu-id="8180d-198">UDT `newtype LittleEndian = Qubit[]` 記載基礎暫存器的使用和解讀方式，進而提供其基底類型的其他表達。</span><span class="sxs-lookup"><span data-stu-id="8180d-198">A UDT `newtype LittleEndian = Qubit[]` documents how the   underlying register is to be used and interpreted, and thus   provides additional expressiveness over its base type.</span></span>

- <span data-ttu-id="8180d-199">除非絕對必要，否則⛔️**不**引進存取子函式;  在此情況下，強烈偏好命名專案。</span><span class="sxs-lookup"><span data-stu-id="8180d-199">⛔️ **DON'T** introduce accessor functions unless strictly required;   strongly prefer named items in this case.</span></span>

  <span data-ttu-id="8180d-200">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-200">*Examples:*</span></span>
  - <span data-ttu-id="8180d-201">`newtype Complex = (Double, Double)`引進 UDT 時，建議您修改定義，以 `newtype Complex = (Real : Double, Imag : Double)` 介紹 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double`函數。</span><span class="sxs-lookup"><span data-stu-id="8180d-201">When introducing a UDT `newtype Complex = (Double, Double)`,   prefer modifying the definition to   `newtype Complex = (Real : Double, Imag : Double)` to introducing   functions `GetReal : Complex -> Double` and   `GetImag : Complex -> Double`.</span></span>

## <a name="namespaces-and-organization"></a><span data-ttu-id="8180d-202">命名空間和組織</span><span class="sxs-lookup"><span data-stu-id="8180d-202">Namespaces and Organization</span></span>

<span data-ttu-id="8180d-203">**主要原則：** 選擇可預測的命名空間名稱，並在每個命名空間中清楚地傳達函數、作業和使用者定義類型的用途。</span><span class="sxs-lookup"><span data-stu-id="8180d-203">**Key principle:** choose namespace names that are predictable and that clearly communicate the purpose of functions, operations, and user-defined types in each namespace.</span></span>

- <span data-ttu-id="8180d-204">✅**將命名空間命名為**`Publisher.Product.DomainArea`。</span><span class="sxs-lookup"><span data-stu-id="8180d-204">✅ **DO** name namespaces as `Publisher.Product.DomainArea`.</span></span>

  <span data-ttu-id="8180d-205">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-205">*Examples:*</span></span>
  - <span data-ttu-id="8180d-206">由 Microsoft 發佈的函式、作業和 Udt，屬於量子開發工具組的量子模擬功能，會放在 `Microsoft.Quantum.Simulation` 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="8180d-206">Functions, operations, and UDTs published by Microsoft as a   part of the quantum simulation feature of the Quantum   Development Kit are placed in the   `Microsoft.Quantum.Simulation` namespace.</span></span>
  - <span data-ttu-id="8180d-207">`Microsoft.Quantum.Math` 代表 Microsoft 發佈的命名空間，做為與數學網域區域相關的量子開發工具組的一部分。</span><span class="sxs-lookup"><span data-stu-id="8180d-207">`Microsoft.Quantum.Math` represents a namespace   published by Microsoft as part of the Quantum Development   Kit pertaining to the mathematics domain area.</span></span>

- <span data-ttu-id="8180d-208">✅ 會將用於特定功能的作業、函式和使用者定義型別放入描述該功能的命名空間中，即使該功能是在不同的問題網域中使用也**是如此。**</span><span class="sxs-lookup"><span data-stu-id="8180d-208">✅ **DO** place operations, functions, and user-defined types used   for specific functionality into a namespace that describes that   functionality, even when that functionality is used across   different problem domains.</span></span>

  <span data-ttu-id="8180d-209">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-209">*Examples:*</span></span>
  - <span data-ttu-id="8180d-210">Microsoft 發佈的狀態準備 Api 會納入「量子開發工具組」中，並放在 `Microsoft.Quantum.Preparation`中。</span><span class="sxs-lookup"><span data-stu-id="8180d-210">State preparation APIs published by Microsoft as a part of   the Quantum Development Kit would be placed into   `Microsoft.Quantum.Preparation`.</span></span>
  - <span data-ttu-id="8180d-211">Microsoft 在配量開發工具組中發佈的量子模擬 Api 會放入 `Microsoft.Quantum.Simulation`。</span><span class="sxs-lookup"><span data-stu-id="8180d-211">Quantum simulation APIs published by Microsoft as a part of the Quantum   Development Kit would be placed into   `Microsoft.Quantum.Simulation`.</span></span>

- <span data-ttu-id="8180d-212">✅ 將只在特定網域內使用的作業、函式和使用者定義類型，**放入表示**其公用程式網域的命名空間。</span><span class="sxs-lookup"><span data-stu-id="8180d-212">✅ **DO** place operations, functions, and user-defined types used only within specific domains into namespaces indicating their domain of utility.</span></span> <span data-ttu-id="8180d-213">如有需要，請使用子命名空間來指示每個網域特定命名空間中的焦點工作。</span><span class="sxs-lookup"><span data-stu-id="8180d-213">If needed, use subnamespaces to indicate focused tasks within each domain-specific namespace.</span></span>

  <span data-ttu-id="8180d-214">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-214">*Examples:*</span></span>
  - <span data-ttu-id="8180d-215">Microsoft 所發佈的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets" 命名空間所提供。</span><span class="sxs-lookup"><span data-stu-id="8180d-215">The quantum machine learning library published by Microsoft is largely   placed into the @"microsoft.quantum.machinelearning" namespace, but example   datasets are provided by the @"microsoft.quantum.machinelearning.datasets"   namespace.</span></span>
  - <span data-ttu-id="8180d-216">Microsoft 在配量開發工具組中發佈的量子化學 Api 應該放入 `Microsoft.Quantum.Chemistry`。</span><span class="sxs-lookup"><span data-stu-id="8180d-216">Quantum chemistry APIs published by Microsoft as a part of the Quantum Development Kit should be placed into `Microsoft.Quantum.Chemistry`.</span></span> <span data-ttu-id="8180d-217">執行約旦--Wigner 分解特有的功能可能會放在 `Microsoft.Quantum.Chemistry.JordanWigner`中，因此 [量子化學] 領域區域的主要介面不會與「處理」相關。</span><span class="sxs-lookup"><span data-stu-id="8180d-217">Functionality specific to implementing the Jordan--Wigner decomposition may be placed in `Microsoft.Quantum.Chemistry.JordanWigner`, so that the primary interface for the quantum chemistry domain area is not concerned with implementations.</span></span>

<span data-ttu-id="8180d-218">**主要原則：** 將命名空間和存取修飾詞一起使用，以刻意瞭解對使用者公開的 API 介面，並隱藏與 Api 的執行和測試相關的內部詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8180d-218">**Key principle:** Use namespaces and access modifiers together to be intentional about the API surface exposed to users, and to hide internal details related to implementation and testing of your APIs.</span></span>

- <span data-ttu-id="8180d-219">✅ 在合理的情況下，請將執行 API 所需的所有函式和**作業放入**與所要執行的 api 相同的命名空間中，但以 "private" 或 "internal" 關鍵字標示，表示它們不是程式庫公用 api 介面的一部分。</span><span class="sxs-lookup"><span data-stu-id="8180d-219">✅ Whenever reasonable, **DO** place all functions and operations needed to implement an API into the same namespace as the API being implemented, but marked with the "private" or "internal" keywords to indicate that they are not part of the public API surface for a library.</span></span> <span data-ttu-id="8180d-220">使用以底線（`_`）開頭的名稱，以視覺化方式區分公用 callables 的私用和內部作業和函式。</span><span class="sxs-lookup"><span data-stu-id="8180d-220">Use a name beginning with an underscore (`_`) to visually distinguish private and internal operations and functions from public callables.</span></span>

  <span data-ttu-id="8180d-221">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-221">*Examples:*</span></span>
  - <span data-ttu-id="8180d-222">作業名稱 `_Features` 表示對指定的命名空間和元件而言是私用的函式，而且應該伴隨 `internal` 關鍵字。</span><span class="sxs-lookup"><span data-stu-id="8180d-222">The operation name `_Features` indicates a function that is   private to a given namespace and assembly, and should be   accompanied by either the `internal` keyword.</span></span>

- <span data-ttu-id="8180d-223">✅ 在罕見的情況下，需要一組豐富的私用函式或作業來執行給定命名空間的 API **，請**將它們放在新的命名空間中，以符合所要執行和結束于 `.Private`中的命名空間。</span><span class="sxs-lookup"><span data-stu-id="8180d-223">✅ In the rare case that an extensive set of private functions or operations are needed to implement the API for a given namespace, **DO** place them in a new namespace matching the namespace being implemented and ending in `.Private`.</span></span>

- <span data-ttu-id="8180d-224">✅ 會將所有單元測試都**放入符合**受測命名空間的命名空間中，並以 `.Tests`結束。</span><span class="sxs-lookup"><span data-stu-id="8180d-224">✅ **DO** place all unit tests into namespaces matching the     namespace under test and ending in `.Tests`.</span></span>

## <a name="naming-conventions-and-vocabulary"></a><span data-ttu-id="8180d-225">命名慣例和詞彙</span><span class="sxs-lookup"><span data-stu-id="8180d-225">Naming Conventions and Vocabulary</span></span>

<span data-ttu-id="8180d-226">**主要原則：** 在各種不同的物件上選擇清楚、可存取且可讀取的名稱和詞彙，包括量子新手和專家。</span><span class="sxs-lookup"><span data-stu-id="8180d-226">**Key principle:** Choose names and terminology that are clear, accessible, and readable across a diverse range of audiences, including both quantum novices and experts.</span></span>

- <span data-ttu-id="8180d-227">⛔️**不**會使用歧視性或 exclusionary 識別碼名稱，也不會有 API 檔批註的術語。</span><span class="sxs-lookup"><span data-stu-id="8180d-227">⛔️ **DON'T** use discriminatory or exclusionary identifier names,   nor terminology in API documentation comments.</span></span>

- <span data-ttu-id="8180d-228">✅**確實**使用 API 檔批註來提供相關的內容、範例和參考，特別是針對更棘手的概念。</span><span class="sxs-lookup"><span data-stu-id="8180d-228">✅ **DO** use API documentation comments to provide relevant   context, examples, and references, especially for more difficult   concepts.</span></span>

- <span data-ttu-id="8180d-229">⛔️**不**會使用不必要難理解的識別碼名稱，或需要重要的量子演算法知識才能讀取。</span><span class="sxs-lookup"><span data-stu-id="8180d-229">⛔️ **DON'T** use identifier names that are unnecessarily esoteric,   or that require significant quantum algorithms knowledge to   read.</span></span>

  <span data-ttu-id="8180d-230">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-230">*Examples:*</span></span>
  - <span data-ttu-id="8180d-231">偏好將「波幅放大反復專案」設為「Grover 反復專案」。</span><span class="sxs-lookup"><span data-stu-id="8180d-231">Prefer "amplitude amplification iteration" to "Grover   iteration."</span></span>

- <span data-ttu-id="8180d-232">✅**確實**會選擇作業和函式名稱，以清楚地傳達所預期的可呼叫效果，而不是其執行方式。</span><span class="sxs-lookup"><span data-stu-id="8180d-232">✅ **DO** choose operations and function names that clearly communicate the intended effect of a callable, and not its implementation.</span></span> <span data-ttu-id="8180d-233">請注意，執行可以和應該是</span><span class="sxs-lookup"><span data-stu-id="8180d-233">Note that the implementation can and should be</span></span>

  <span data-ttu-id="8180d-234">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-234">*Examples:*</span></span>
  - <span data-ttu-id="8180d-235">偏好「估計重迭」為「Hadamard 測試」，因為後者會傳達前者的實值。</span><span class="sxs-lookup"><span data-stu-id="8180d-235">Prefer "estimate overlap" to "Hadamard test," as the latter   communicates how the former is implemented.</span></span>

- <span data-ttu-id="8180d-236">✅**在**所有 Q\# api 之間以一致的方式使用單字：</span><span class="sxs-lookup"><span data-stu-id="8180d-236">✅ **DO** use words in a consistent fashion across all Q\# APIs:</span></span>

  - <span data-ttu-id="8180d-237">**之外**</span><span class="sxs-lookup"><span data-stu-id="8180d-237">**Verbs:**</span></span>

    - <span data-ttu-id="8180d-238">判斷**提示：檢查**有關目的電腦及其 qubits 狀態的假設，可能是使用 unphysical 資源。</span><span class="sxs-lookup"><span data-stu-id="8180d-238">**Assert**: Check that an assumption about the state of a target machine and its qubits holds, possibly by using unphysical resources.</span></span> <span data-ttu-id="8180d-239">使用此動詞命令的作業應一律安全地卸載，而不會影響程式庫和可執行程式的功能。</span><span class="sxs-lookup"><span data-stu-id="8180d-239">Operations using this verb should always be safely removable without affecting the functionality of libraries and executable programs.</span></span> <span data-ttu-id="8180d-240">請注意，與事實不同的是，判斷提示一般可能會依賴外部狀態，例如 qubit 暫存器的狀態、執行環境等等。</span><span class="sxs-lookup"><span data-stu-id="8180d-240">Note that unlike facts, assertions may in general depend on external state, such as the state of a qubit register, the execution environment or so forth.</span></span> <span data-ttu-id="8180d-241">因為對外部狀態的相依性是一種副作用，所以判斷提示必須公開為作業，而不是函數。</span><span class="sxs-lookup"><span data-stu-id="8180d-241">As dependency on external state is a kind of side effect, assertions must be exposed as operations rather than functions.</span></span>

    - <span data-ttu-id="8180d-242">**估計**：使用一或多個可能重複的測量，從測量結果估計傳統數量。</span><span class="sxs-lookup"><span data-stu-id="8180d-242">**Estimate**: Using one or more possibly repeated   measurements, estimate a classical quantity from   measurement results.</span></span>

      <span data-ttu-id="8180d-243">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-243">*Examples:*</span></span>
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - <span data-ttu-id="8180d-244">**準備**：將配量作業或作業順序套用至一或多個假設以特定初始狀態啟動的 qubits （通常是 $ \ket{00\cdots 0} $），這會導致這些 qubits 的狀態演變成所需的結束狀態。</span><span class="sxs-lookup"><span data-stu-id="8180d-244">**Prepare**: Apply a quantum operation or sequence of operations to one or more qubits assumed to start in a particular initial state (typically $\ket{00\cdots 0}$), causing the state of those qubits to evolve to a desired end state.</span></span> <span data-ttu-id="8180d-245">一般來說，在指定的啟動狀態以外的狀態下，**可能會**產生未定義的單一轉換，但仍**應**保留作業及其 adjoint 的「取消」並套用非 op。</span><span class="sxs-lookup"><span data-stu-id="8180d-245">In general, acting on states other than the given starting state **MAY** result in an undefined unitary transformation, but **SHOULD** still preserve that an operation and its adjoint "cancel out" and apply a no-op.</span></span>

      <span data-ttu-id="8180d-246">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-246">*Examples:*</span></span>
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - <span data-ttu-id="8180d-247">**量值**：將配量作業或作業順序套用至一或多個 qubits，並讀取傳統資料。</span><span class="sxs-lookup"><span data-stu-id="8180d-247">**Measure**: Apply a quantum operation or sequence of   operations to one or more qubits, reading classical data   back out.</span></span>

      <span data-ttu-id="8180d-248">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-248">*Examples:*</span></span>
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - <span data-ttu-id="8180d-249">**Apply**：將配量作業或作業順序套用至一或多個 qubits，使這些 qubits 的狀態以一致的方式變更。</span><span class="sxs-lookup"><span data-stu-id="8180d-249">**Apply**: Apply a quantum operation or sequence of operations to one or more qubits, causing the state of those qubits to change in a coherent fashion.</span></span> <span data-ttu-id="8180d-250">這個動詞是 Q\# 的命名法中最一般的動詞，**不應**在更特定的動詞更直接相關時使用。</span><span class="sxs-lookup"><span data-stu-id="8180d-250">This verb is the most general verb in Q\# nomenclature, and **SHOULD NOT BE** used when a more specific verb is more directly relevant.</span></span>

  - <span data-ttu-id="8180d-251">**名詞**：</span><span class="sxs-lookup"><span data-stu-id="8180d-251">**Nouns**:</span></span>

    - <span data-ttu-id="8180d-252">**事實**：僅取決於其輸入，而不是目的電腦的狀態、其環境或電腦 qubits 狀態的布林值條件。</span><span class="sxs-lookup"><span data-stu-id="8180d-252">**Fact**: A Boolean condition which depends only on its inputs and not on the state of a target machine, its environment, or the state of the machine's qubits.</span></span> <span data-ttu-id="8180d-253">相較于判斷提示，事實只對提供給該事實的*值*是敏感的。</span><span class="sxs-lookup"><span data-stu-id="8180d-253">By contrast with an assertion, a fact is only sensitive to the *values* provided to that fact.</span></span> <span data-ttu-id="8180d-254">例如：</span><span class="sxs-lookup"><span data-stu-id="8180d-254">For example:</span></span>

      <span data-ttu-id="8180d-255">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-255">*Examples:*</span></span>
      - <span data-ttu-id="8180d-256">@"microsoft.quantum.diagnostics.equalityfacti"：代表兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或不會與任何其他程式狀態無關。</span><span class="sxs-lookup"><span data-stu-id="8180d-256">@"microsoft.quantum.diagnostics.equalityfacti": represents an equality fact about two integer inputs; either the integers provided as input are equal to each other, or they are not, independent of any other program state.</span></span>

    - <span data-ttu-id="8180d-257">**選項：** UDT，其中包含數個命名專案，可以做為函式或作業的「選擇性引數」。</span><span class="sxs-lookup"><span data-stu-id="8180d-257">**Options:** A UDT containing several named items that can act as "optional arguments" to a function or operation.</span></span> <span data-ttu-id="8180d-258">例如：</span><span class="sxs-lookup"><span data-stu-id="8180d-258">For example:</span></span>

      <span data-ttu-id="8180d-259">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-259">*Examples:*</span></span>
      - <span data-ttu-id="8180d-260">@"microsoft.quantum.machinelearning.trainingoptions" UDT 包含學習速率的命名專案、迷你批次大小，以及適用于 ML 訓練的其他可設定參數。</span><span class="sxs-lookup"><span data-stu-id="8180d-260">The @"microsoft.quantum.machinelearning.trainingoptions" UDT includes named items for learning rate, minibatch size, and other configurable parameters for ML training.</span></span>

  - <span data-ttu-id="8180d-261">**形容詞**：</span><span class="sxs-lookup"><span data-stu-id="8180d-261">**Adjectives**:</span></span>

    - <span data-ttu-id="8180d-262">⛔️ **New**：**不應**使用此形容詞，以避免在許多程式設計語言中將其使用方式與動詞（例如： C++、 C#、JAVA、TypeScript、PowerShell）混淆。</span><span class="sxs-lookup"><span data-stu-id="8180d-262">⛔️ **New**: This adjective **SHOULD NOT** be used, as to avoid confusion   with its usage as a verb in many   programming languages (e.g.: C++, C#, Java, TypeScript, PowerShell).</span></span>

  - <span data-ttu-id="8180d-263">**介係詞：** 在某些情況下，介係詞可以用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。</span><span class="sxs-lookup"><span data-stu-id="8180d-263">**Prepositions:** In some cases, prepositions can be used to further disambiguate or clarify the roles of nouns and verbs in function and operation names.</span></span> <span data-ttu-id="8180d-264">不過，請務必謹慎且一致地採取此動作。</span><span class="sxs-lookup"><span data-stu-id="8180d-264">Care should be taken to do so sparingly and consistently, however.</span></span>

    - <span data-ttu-id="8180d-265">**As：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示**為** *X* ，而不是其原始標記法。</span><span class="sxs-lookup"><span data-stu-id="8180d-265">**As:** Represents that a function's input and output represent the same information, but that the output represents that information **as** an *X* instead of its original representation.</span></span> <span data-ttu-id="8180d-266">這對於型別轉換函式而言特別常見。</span><span class="sxs-lookup"><span data-stu-id="8180d-266">This is especially common for type conversion functions.</span></span>

      <span data-ttu-id="8180d-267">*範例：*</span><span class="sxs-lookup"><span data-stu-id="8180d-267">*Examples:*</span></span>
      - <span data-ttu-id="8180d-268">`IntAsDouble(2)` 表示輸入（`2`）和輸出（`2.0`）代表品質相同的資訊，但使用不同的 Q\# 資料類型來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="8180d-268">`IntAsDouble(2)` indicates that both the input (`2`) and the output (`2.0`)   represent qualitatively the same information, but using   different Q\# data types to do so.</span></span>

    - <span data-ttu-id="8180d-269">**來源：** 若要確保一致性，此介係詞**不應該**用來表示類型轉換函式，或任何其他**適合的情況**。</span><span class="sxs-lookup"><span data-stu-id="8180d-269">**From:** To ensure consistency, this preposition   **SHOULD NOT** be used to indicate type conversion   functions or any other case where **As** is appropriate.</span></span>

    - <span data-ttu-id="8180d-270">⛔️**為：** **不應**使用此介係詞，因為它會與許多程式設計語言中的動詞一起使用，以避免混淆。</span><span class="sxs-lookup"><span data-stu-id="8180d-270">⛔️ **To:** This preposition **SHOULD NOT** be used, as to   avoid confusion with its usage as a verb in many   programming languages.</span></span>
