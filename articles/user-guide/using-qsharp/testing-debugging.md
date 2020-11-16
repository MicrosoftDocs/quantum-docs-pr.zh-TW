---
title: 測試和偵錯
description: 瞭解如何使用單元測試、事實和判斷提示，以及傾印函式來測試和偵測量副程式。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690968"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="51afd-103">測試和偵錯</span><span class="sxs-lookup"><span data-stu-id="51afd-103">Testing and debugging</span></span>

<span data-ttu-id="51afd-104">就像傳統程式設計一樣，必須能夠檢查量副程式是否正常運作，並且能夠診斷不正確的行為。</span><span class="sxs-lookup"><span data-stu-id="51afd-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="51afd-105">在本節中，我們將討論 Q# 針對量副程式進行測試和偵測所提供的工具。</span><span class="sxs-lookup"><span data-stu-id="51afd-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="51afd-106">單元測試</span><span class="sxs-lookup"><span data-stu-id="51afd-106">Unit Tests</span></span>

<span data-ttu-id="51afd-107">測試傳統程式的其中一個常見方法是撰寫稱為 *單元測試* 的小程式，以在程式庫中執行程式碼，並將其輸出與某些預期輸出進行比較。</span><span class="sxs-lookup"><span data-stu-id="51afd-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="51afd-108">例如，您可以確定 `Square(2)` `4` 因為您知道 $ 2 ^ 2 = $4 的 *先驗* ，所以會傳回。</span><span class="sxs-lookup"><span data-stu-id="51afd-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="51afd-109">Q# 支援建立量副程式的單元測試，並可在 [xUnit](https://xunit.github.io/) 單元測試架構中以測試的形式執行。</span><span class="sxs-lookup"><span data-stu-id="51afd-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="51afd-110">建立測試專案</span><span class="sxs-lookup"><span data-stu-id="51afd-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="51afd-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="51afd-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="51afd-112">開啟 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="51afd-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="51afd-113">移 **至 [檔案** ] 功能表，然後選取 [ **新增 > 專案** ...]。在右上角，搜尋 `Q#` 並選取 [ **Q# 測試專案** ] 範本。</span><span class="sxs-lookup"><span data-stu-id="51afd-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="51afd-114">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51afd-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="51afd-115">從您最愛的命令列執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="51afd-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="51afd-116">您的新專案有一個單一檔案 `Tests.qs` ，它提供了一個方便的位置來定義新的 Q# 單元測試。</span><span class="sxs-lookup"><span data-stu-id="51afd-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="51afd-117">一開始，這個檔案包含一個範例單元測試， `AllocateQubit` 它會檢查新配置的量子位是否處於 $ \ket {0} $ 狀態並列印訊息：</span><span class="sxs-lookup"><span data-stu-id="51afd-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="51afd-118">任何 Q# 採用型別和傳回之引數的作業或函數，都 `Unit` `Unit` 可以透過屬性標示為單元測試 `@Test("...")` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="51afd-119">在上述範例中，該屬性的引數會 `"QuantumSimulator"` 指定測試執行的目標。</span><span class="sxs-lookup"><span data-stu-id="51afd-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="51afd-120">單一測試可以在多個目標上執行。</span><span class="sxs-lookup"><span data-stu-id="51afd-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="51afd-121">例如，在之前加入屬性 `@Test("ResourcesEstimator")` `AllocateQubit` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="51afd-122">儲存檔案並執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="51afd-122">Save the file and run all tests.</span></span> <span data-ttu-id="51afd-123">現在應該會有兩個單元測試，一個在 `AllocateQubit` 上執行 `QuantumSimulator` ，另一個在上執行 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="51afd-124">編譯器會將 Q# 內建目標 `"QuantumSimulator"` 、 `"ToffoliSimulator"` 和 `"ResourcesEstimator"` 視為單元測試的有效執行目標。</span><span class="sxs-lookup"><span data-stu-id="51afd-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="51afd-125">您也可以指定任何完整名稱來定義自訂的執行目標。</span><span class="sxs-lookup"><span data-stu-id="51afd-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="51afd-126">執行 Q# 單元測試</span><span class="sxs-lookup"><span data-stu-id="51afd-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="51afd-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="51afd-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="51afd-128">在每個解決方案的一次性設定中，移至 [ **測試** ] 功能表，然後選取 [ **測試設定] > 預設的處理器架構 > X64** ]。</span><span class="sxs-lookup"><span data-stu-id="51afd-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="51afd-129">Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項 () 檔案中 `.suo` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="51afd-130">如果您刪除此檔案，則需要再次選取 **X64** 作為處理器架構。</span><span class="sxs-lookup"><span data-stu-id="51afd-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="51afd-131">建立專案，開啟 [ **測試** ] 功能表，然後選取 [ **Windows > 測試瀏覽器** ]。</span><span class="sxs-lookup"><span data-stu-id="51afd-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="51afd-132">**AllocateQubit** 會顯示在 [ **未執行的測試** ] 群組中的測試清單中。</span><span class="sxs-lookup"><span data-stu-id="51afd-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="51afd-133">選取 [ **全部執行** ] 或 [執行這個個別測試]。</span><span class="sxs-lookup"><span data-stu-id="51afd-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="51afd-134">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51afd-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="51afd-135">若要執行測試，請流覽至專案資料夾 (包含) 的資料夾 `Tests.csproj` ，然後執行命令：</span><span class="sxs-lookup"><span data-stu-id="51afd-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="51afd-136">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="51afd-136">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="51afd-137">您可以根據其名稱或執行目標來篩選單元測試：</span><span class="sxs-lookup"><span data-stu-id="51afd-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="51afd-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="51afd-138">\*\*_</span></span>

<span data-ttu-id="51afd-139">內建函數 <xref:Microsoft.Quantum.Intrinsic.Message> 具有類型 `(String -> Unit)` ，可讓您建立診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="51afd-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="51afd-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="51afd-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="51afd-141">在測試瀏覽器中執行測試並按一下測試之後，面板會顯示測試回合的相關資訊：通過/失敗狀態、經過時間，以及輸出的連結。</span><span class="sxs-lookup"><span data-stu-id="51afd-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="51afd-142">按一下 [_ *輸出* \*]，以在新視窗中開啟測試輸出。</span><span class="sxs-lookup"><span data-stu-id="51afd-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="51afd-144">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51afd-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="51afd-145">每項測試的通過/失敗狀態都會列印到主控台 `dotnet test` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="51afd-146">針對失敗的測試，輸出也會列印到主控台，以協助診斷失敗。</span><span class="sxs-lookup"><span data-stu-id="51afd-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="51afd-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="51afd-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="51afd-148">事實和判斷提示</span><span class="sxs-lookup"><span data-stu-id="51afd-148">Facts and Assertions</span></span>

<span data-ttu-id="51afd-149">因為中的函式沒有 Q# _邏輯_ 副作用，所以您永遠不會在程式中觀察到 Q# 任何其他類型的效果，從執行其輸出類型為空元組的函式 `()` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-149">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="51afd-150">也就是說，目的電腦可以選擇不執行任何會傳回的函式，以 `()` 保證此省略不會修改任何下列程式碼的行為 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51afd-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="51afd-151">此行為可讓函式傳回 `()` (，例如 `Unit`) 將判斷提示和偵測邏輯內嵌到程式中的有用工具 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51afd-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="51afd-152">讓我們來看一個簡單的範例：</span><span class="sxs-lookup"><span data-stu-id="51afd-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="51afd-153">在這裡，關鍵字 `fail` 表示計算不應繼續，並且會在執行程式的目的電腦上引發例外狀況 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51afd-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="51afd-154">根據定義，無法從內觀察到這類失敗 Q# ，因為目的電腦在到達語句之後就不再執行程式 Q# 代碼 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-154">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="51afd-155">因此，如果我們繼續進行呼叫 `PositivityFact` ，我們可以確保其輸入是正面的。</span><span class="sxs-lookup"><span data-stu-id="51afd-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="51afd-156">請注意，我們可以 `PositivityFact` 使用 [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) 命名空間中的函式來執行相同的行為 <xref:Microsoft.Quantum.Diagnostics> ：</span><span class="sxs-lookup"><span data-stu-id="51afd-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="51afd-157">相反地，_Assertions \* 的用途類似于事實，但可能取決於目的電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="51afd-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="51afd-158">同樣地，它們會定義為作業，而事實會定義為函式 (如先前範例) 。</span><span class="sxs-lookup"><span data-stu-id="51afd-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="51afd-159">若要瞭解差異，請考慮在判斷提示中使用下列事實：</span><span class="sxs-lookup"><span data-stu-id="51afd-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="51afd-160">在這裡，我們會使用作業 <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> 來傳回可使用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="51afd-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="51afd-161">由於這取決於程式的全域狀態及其執行環境，我們的定義 `AssertQubitsAreAvailable` 也必須是一項作業。</span><span class="sxs-lookup"><span data-stu-id="51afd-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="51afd-162">不過，我們可以使用該全域狀態來產生簡單的 `Bool` 值做為函數的輸入 `Fact` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="51afd-163">[序言](xref:microsoft.quantum.libraries.standard.prelude)是以這些概念為基礎，提供兩個特別有用的判斷提示， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 並將 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 模型化為作業 `()` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="51afd-164">這些判斷提示各採用 Pauli 運算子，以描述感興趣的特定量值、執行測量的量子暫存器，以及假設結果。</span><span class="sxs-lookup"><span data-stu-id="51afd-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="51afd-165">由模擬運作的目的電腦不會受到 [無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的系結，而且可以執行這類度量，而不會干擾傳遞至這類判斷提示的暫存器。</span><span class="sxs-lookup"><span data-stu-id="51afd-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="51afd-166">然後，模擬器可以像之前的函式一樣 `PositivityFact` ，在實務中未觀察到假設結果時停止計算：</span><span class="sxs-lookup"><span data-stu-id="51afd-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="51afd-167">在不復制定理可防止檢查量子狀態的實體量子硬體上， `AssertMeasurement` 和作業只會傳回而 `AssertMeasurementProbability` 不會 `()` 有其他效果。</span><span class="sxs-lookup"><span data-stu-id="51afd-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="51afd-168"><xref:Microsoft.Quantum.Diagnostics>命名空間會提供更多的系列函式 `Assert` ，讓您可以檢查更多的 advanced 條件。</span><span class="sxs-lookup"><span data-stu-id="51afd-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="51afd-169">傾印函式</span><span class="sxs-lookup"><span data-stu-id="51afd-169">Dump Functions</span></span>

<span data-ttu-id="51afd-170">為協助針對量副程式進行疑難排解， <xref:Microsoft.Quantum.Diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 。</span><span class="sxs-lookup"><span data-stu-id="51afd-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="51afd-171">產生的輸出取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="51afd-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="51afd-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="51afd-172">DumpMachine</span></span>

<span data-ttu-id="51afd-173">以量子開發工具組的一部分散發的全狀態量子模擬器，會寫入整個量子系統的 [wave](https://en.wikipedia.org/wiki/Wave_function) 函式檔案，做為一維的複數陣列，其中每個元素都代表測量計算基礎狀態 $ \ket{n} $ 之機率的波幅，其中 $ \ket{n} = \ket{b_ {n-1} .。。b_1b_0} $ 代表位 $ \{ b_i \} $。</span><span class="sxs-lookup"><span data-stu-id="51afd-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="51afd-174">例如，在只有兩個量子位的電腦上配置且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } \ket 中 {2} {10} ，\end{align} $ $ 呼叫會 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="51afd-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="51afd-175">第一個資料列會以其重大順序提供批註，內含對應量子位的識別碼。</span><span class="sxs-lookup"><span data-stu-id="51afd-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="51afd-176">其餘的資料列描述測量以笛卡兒和極座標形式測量基礎狀態向量 $ \ket{n} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="51afd-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="51afd-177">第一列的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="51afd-177">In detail for the first row:</span></span>

* <span data-ttu-id="51afd-178">**`∣0❭:`** 此資料列對應于 `0` 計算基礎狀態</span><span class="sxs-lookup"><span data-stu-id="51afd-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="51afd-179">**`0.707107 +  0.000000 i`** ：笛卡兒格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="51afd-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="51afd-180">**` == `** ： `equal` 符號會分隔兩個對等的表示。</span><span class="sxs-lookup"><span data-stu-id="51afd-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="51afd-181">**`**********  `** ：量值的圖形表示，的數目 `*` 會與測量這個狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="51afd-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="51afd-182">**`[ 0.500000 ]`** ：量值的數值</span><span class="sxs-lookup"><span data-stu-id="51afd-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="51afd-183">**`    ---`** ：振幅階段的圖形表示 (查看下列輸出) 。</span><span class="sxs-lookup"><span data-stu-id="51afd-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="51afd-184">**`[ 0.0000 rad ]`** ：階段的數值 (弧度) 。</span><span class="sxs-lookup"><span data-stu-id="51afd-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="51afd-185">大小和階段都會以圖形表示顯示。</span><span class="sxs-lookup"><span data-stu-id="51afd-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="51afd-186">大小表示是很簡單的：它會顯示一個橫條，也就是 `*` 更大的機率。</span><span class="sxs-lookup"><span data-stu-id="51afd-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="51afd-187">在階段中，我們會根據範圍顯示下列符號來代表角度：</span><span class="sxs-lookup"><span data-stu-id="51afd-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="51afd-188">下列範例顯示 `DumpMachine` 一些常見狀態：</span><span class="sxs-lookup"><span data-stu-id="51afd-188">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="51afd-189">量子位的識別碼會在執行時間指派，且不一定會與量子位的配置順序或其在量子位暫存器中的位置對齊。</span><span class="sxs-lookup"><span data-stu-id="51afd-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="51afd-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="51afd-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="51afd-191">您可以在程式碼中放入中斷點，並檢查量子位變數的值，以在 Visual Studio 中找出量子位識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="51afd-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中顯示量子位識別碼](~/media/qubit_id.png)
  >
  > <span data-ttu-id="51afd-193">索引為 on 的 `0` 量子位 `register2` 具有 id = `3` ，量子位的索引 `1` 識別碼為 `2` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="51afd-194">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51afd-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="51afd-195">您可以使用函式來尋找量子位識別碼 <xref:Microsoft.Quantum.Intrinsic.Message> ，並在訊息中傳遞量子位變數，例如：</span><span class="sxs-lookup"><span data-stu-id="51afd-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="51afd-196">這可能會產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="51afd-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="51afd-197">這表示具有 index 的量子位 `0` `register2` 具有 id =，而 `3` 索引的量子位具有 `1` id = `2` 。</span><span class="sxs-lookup"><span data-stu-id="51afd-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="51afd-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="51afd-198">\*\*_</span></span>

<span data-ttu-id="51afd-199">因為 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 是  <xref:Microsoft.Quantum.Diagnostics> 命名空間的一部分，所以您必須加入 `open` 語句來存取它：</span><span class="sxs-lookup"><span data-stu-id="51afd-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="51afd-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="51afd-200">DumpRegister</span></span>

<span data-ttu-id="51afd-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> 的運作方式 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，不同之處在于它也會採用量子位的陣列，將資訊數量限制為只有與相對應的量子位相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="51afd-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="51afd-202">同樣地 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，所產生的資訊 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="51afd-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="51afd-203">針對完整狀態量子模擬器，它會寫入至檔案，而 wave 函式是由所提供量子位所產生的量子子系統全域階段所產生，其格式與相同 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 。</span><span class="sxs-lookup"><span data-stu-id="51afd-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="51afd-204">例如，再一次重新執行一部只配置了兩個量子位的電腦，並在量子州 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } {2} \ket {10} =-e ^ {-i \ pi/4} ( ( \frac {1} {\sqrt {2} } \ket {0} -\frac{ (1 + i) } {2} \ket {1} ) \otimes {2} } \frac{- {0} (\end{align} $ $ 呼叫 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 以 `qubit[0]` 產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="51afd-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="51afd-205">而且，呼叫 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 以 `qubit[1]` 產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="51afd-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="51afd-206">一般情況下，使用另一個暫存器纏結的暫存器狀態是混合的狀態，而不是單純的狀態。</span><span class="sxs-lookup"><span data-stu-id="51afd-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="51afd-207">在此情況下，會 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 輸出下列訊息：</span><span class="sxs-lookup"><span data-stu-id="51afd-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="51afd-208">下列範例會示範如何 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 在程式碼中使用和 Q# ：</span><span class="sxs-lookup"><span data-stu-id="51afd-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="51afd-209">偵錯</span><span class="sxs-lookup"><span data-stu-id="51afd-209">Debugging</span></span>

<span data-ttu-id="51afd-210">在和函 `Assert` 式 `Dump` 和作業之上， Q# 支援標準 Visual Studio 偵錯工具功能的子集： [設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)，以及在模擬器上執行您的程式碼時，可以 [檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) 。</span><span class="sxs-lookup"><span data-stu-id="51afd-210">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="51afd-211">在 Visual Studio Code 中的偵錯工具會利用 c # 針對 OmniSharp 所支援的 Visual Studio Code 擴充功能所提供的偵錯工具，且需要安裝 [最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="51afd-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
