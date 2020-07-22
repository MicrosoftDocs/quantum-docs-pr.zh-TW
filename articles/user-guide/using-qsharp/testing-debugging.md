---
title: 測試和偵錯
description: 瞭解如何使用單元測試、事實和判斷提示，以及傾印函式來測試和偵測量副程式。
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: db6e49e94e5ceb3b1b0b2d6ab57391618084072b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870969"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="23322-103">測試和偵錯</span><span class="sxs-lookup"><span data-stu-id="23322-103">Testing and debugging</span></span>

<span data-ttu-id="23322-104">就像傳統程式設計一樣，要能夠檢查配量程式是否符合預期，以及能夠診斷不正確的行為，是不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="23322-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="23322-105">在本節中，我們將討論 Q # 提供的工具，以測試和偵測量副程式。</span><span class="sxs-lookup"><span data-stu-id="23322-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="23322-106">單元測試</span><span class="sxs-lookup"><span data-stu-id="23322-106">Unit Tests</span></span>

<span data-ttu-id="23322-107">測試傳統程式的一個常見方法是撰寫稱為「*單元測試*」的小型程式，這會在程式庫中執行程式碼，並將其輸出與某些預期的輸出做比較。</span><span class="sxs-lookup"><span data-stu-id="23322-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="23322-108">例如，您可以確保傳回， `Square(2)` `4` 因為您知道 $ 2 ^ 2 = $4 的*先驗*。</span><span class="sxs-lookup"><span data-stu-id="23322-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="23322-109">問 # 支援針對量副程式建立單元測試，並可在[xUnit](https://xunit.github.io/)單元測試架構中作為測試執行。</span><span class="sxs-lookup"><span data-stu-id="23322-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="23322-110">建立測試專案</span><span class="sxs-lookup"><span data-stu-id="23322-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="23322-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23322-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="23322-112">開啟 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="23322-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="23322-113">移**至 [檔案] 功能表，然後**選取 [新增] **> 專案**...]。在右上角搜尋 `Q#` ，然後選取 [ **Q # 測試] 專案**範本。</span><span class="sxs-lookup"><span data-stu-id="23322-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="23322-114">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="23322-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="23322-115">從您最愛的命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="23322-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="23322-116">您的新專案具有單一檔案 `Tests.qs` ，可提供方便的位置來定義新的 Q # 單元測試。</span><span class="sxs-lookup"><span data-stu-id="23322-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="23322-117">一開始，這個檔案包含一個範例單元測試， `AllocateQubit` 它會檢查新配置的 qubit 是否處於 $ \ket {0} $ 狀態，並列印一則訊息：</span><span class="sxs-lookup"><span data-stu-id="23322-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="23322-118">任何接受型別和傳回之引數的 Q # 作業或函式，都 `Unit` `Unit` 可以透過屬性標示為單元測試 `@Test("...")` 。</span><span class="sxs-lookup"><span data-stu-id="23322-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="23322-119">在上述範例中，該屬性（attribute）的引數（ `"QuantumSimulator"` ）會指定測試執行所在的目標。</span><span class="sxs-lookup"><span data-stu-id="23322-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="23322-120">單一測試可以在多個目標上執行。</span><span class="sxs-lookup"><span data-stu-id="23322-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="23322-121">例如，在之前加入屬性 `@Test("ResourcesEstimator")` `AllocateQubit` 。</span><span class="sxs-lookup"><span data-stu-id="23322-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="23322-122">儲存檔案並執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="23322-122">Save the file and run all tests.</span></span> <span data-ttu-id="23322-123">現在應該有兩個單元測試，一個在 `AllocateQubit` 上執行，一個在上 `QuantumSimulator` 執行 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="23322-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="23322-124">Q # 編譯器會將內建目標 `"QuantumSimulator"` 、和辨識 `"ToffoliSimulator"` `"ResourcesEstimator"` 為適用于單元測試的有效執行目標。</span><span class="sxs-lookup"><span data-stu-id="23322-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid execution targets for unit tests.</span></span> <span data-ttu-id="23322-125">也可以指定任何完整名稱，以定義自訂的執行目標。</span><span class="sxs-lookup"><span data-stu-id="23322-125">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="23322-126">執行 Q # 單元測試</span><span class="sxs-lookup"><span data-stu-id="23322-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="23322-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23322-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="23322-128">在 [一次] [個別解決方案設定] 中，移至 [**測試**] 功能表，然後選取 [**測試設定] > 預設的處理器架構 > X64**]。</span><span class="sxs-lookup"><span data-stu-id="23322-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="23322-129">Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項（）檔案中 `.suo` 。</span><span class="sxs-lookup"><span data-stu-id="23322-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="23322-130">如果您刪除此檔案，則需要再次選取 [ **X64** ] 做為您的處理器架構。</span><span class="sxs-lookup"><span data-stu-id="23322-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="23322-131">建立專案，開啟 [**測試**] 功能表，然後選取 [ **Windows > test Explorer**]。</span><span class="sxs-lookup"><span data-stu-id="23322-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="23322-132">**AllocateQubit**會顯示在 [**未執行的測試**] 群組中的測試清單中。</span><span class="sxs-lookup"><span data-stu-id="23322-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="23322-133">選取 [**全部執行**] 或 [執行此個別測試]。</span><span class="sxs-lookup"><span data-stu-id="23322-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="23322-134">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="23322-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="23322-135">若要執行測試，請流覽至專案資料夾（包含的資料夾 `Tests.csproj` ），然後執行命令：</span><span class="sxs-lookup"><span data-stu-id="23322-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="23322-136">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="23322-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="23322-137">單元測試可以根據其名稱或執行目標來進行篩選：</span><span class="sxs-lookup"><span data-stu-id="23322-137">Unit tests can be filtered according to their name or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="23322-138">內建函式的 <xref:microsoft.quantum.intrinsic.message> 類型為 `(String -> Unit)` ，可讓您建立診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="23322-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="23322-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23322-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="23322-140">在測試瀏覽器中執行測試並按一下測試之後，會顯示一個面板，其中包含測試執行的相關資訊：通過/失敗狀態、經過時間，以及輸出的連結。</span><span class="sxs-lookup"><span data-stu-id="23322-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test execution: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="23322-141">按一下 [**輸出**]，在新視窗中開啟測試輸出。</span><span class="sxs-lookup"><span data-stu-id="23322-141">Click **Output** to open the test output in a new window.</span></span>

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="23322-143">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="23322-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="23322-144">每項測試的通過/失敗狀態會由列印到主控台 `dotnet test` 。</span><span class="sxs-lookup"><span data-stu-id="23322-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="23322-145">對於失敗的測試，輸出也會列印到主控台，以協助診斷失敗。</span><span class="sxs-lookup"><span data-stu-id="23322-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="23322-146">事實和判斷提示</span><span class="sxs-lookup"><span data-stu-id="23322-146">Facts and Assertions</span></span>

<span data-ttu-id="23322-147">因為 Q # 中的函式沒有_邏輯_副作用，所以您永遠不會觀察到來自于 q # 程式中的任何其他類型的效果，以執行其輸出類型為空元組的函式 `()` 。</span><span class="sxs-lookup"><span data-stu-id="23322-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="23322-148">也就是說，目的電腦可以選擇不執行任何會傳回的函式， `()` 並保證此省略不會修改任何下列 Q 號碼程式碼的行為。</span><span class="sxs-lookup"><span data-stu-id="23322-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="23322-149">此行為可讓函式傳回 `()` （例如 `Unit` ）實用的工具，將判斷提示和偵錯工具內嵌到 Q # 程式中。</span><span class="sxs-lookup"><span data-stu-id="23322-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="23322-150">讓我們來看一個簡單的範例：</span><span class="sxs-lookup"><span data-stu-id="23322-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="23322-151">在這裡，關鍵字 `fail` 指出計算不應繼續，並會在執行 Q # 程式的目的電腦中引發例外狀況。</span><span class="sxs-lookup"><span data-stu-id="23322-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="23322-152">根據定義，無法從 Q # 中觀察到這種失敗，因為目的電腦在到達語句之後，不會再執行 Q # 程式碼 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="23322-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="23322-153">因此，如果我們繼續呼叫 `PositivityFact` ，我們可以確保其輸入是正數。</span><span class="sxs-lookup"><span data-stu-id="23322-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="23322-154">請注意，我們可以 `PositivityFact` 使用 [`Fact`](xref:microsoft.quantum.diagnostics.fact) 命名空間中的函式，來執行與相同的行為 <xref:microsoft.quantum.diagnostics> ：</span><span class="sxs-lookup"><span data-stu-id="23322-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="23322-155">另一方面，*判斷*提示的使用方式類似于事實，但可能取決於目的電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="23322-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="23322-156">同樣地，它們會定義為作業，而事實會定義為函式（如上述範例所示）。</span><span class="sxs-lookup"><span data-stu-id="23322-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="23322-157">若要瞭解差異，請考慮下列在判斷提示內的事實用法：</span><span class="sxs-lookup"><span data-stu-id="23322-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="23322-158">在這裡，我們會使用作業 <xref:microsoft.quantum.environment.getqubitsavailabletouse> 來傳回可供使用的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="23322-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="23322-159">因為這取決於程式及其執行環境的全域狀態，所以的定義 `AssertQubitsAreAvailable` 也必須是作業。</span><span class="sxs-lookup"><span data-stu-id="23322-159">As this depends on the global state of the program and its execution environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="23322-160">不過，我們可以使用該全域狀態來產生簡單的 `Bool` 值做為函數的輸入 `Fact` 。</span><span class="sxs-lookup"><span data-stu-id="23322-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="23322-161">根據這些想法來建立[的序言](xref:microsoft.quantum.libraries.standard.prelude)，提供了兩個特別有用的判斷提示， <xref:microsoft.quantum.diagnostics.assertmeasurement> 並將 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 模型化為作業 `()` 。</span><span class="sxs-lookup"><span data-stu-id="23322-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="23322-162">這些判斷提示各自採用 Pauli 運算子來描述特定量測測量、執行測量的量子暫存器，以及假設結果。</span><span class="sxs-lookup"><span data-stu-id="23322-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="23322-163">模擬使用的目的機器不是由「[無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)」所系結，而且可以執行這類測量，而不會干擾傳遞至這類判斷提示的暫存器。</span><span class="sxs-lookup"><span data-stu-id="23322-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="23322-164">模擬器之後就可以與先前的函式類似 `PositivityFact` ，如果未在實務中觀察到假設結果，就停止計算：</span><span class="sxs-lookup"><span data-stu-id="23322-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

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

<span data-ttu-id="23322-165">在實體量子硬體上，如果沒有複製定理可防止檢查配量狀態，和作業只會傳回，而 `AssertMeasurement` `AssertMeasurementProbability` 不會 `()` 有其他效果。</span><span class="sxs-lookup"><span data-stu-id="23322-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="23322-166"><xref:microsoft.quantum.diagnostics>命名空間提供更多的系列函式 `Assert` ，您可以用它來檢查更先進的條件。</span><span class="sxs-lookup"><span data-stu-id="23322-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="23322-167">傾印函式</span><span class="sxs-lookup"><span data-stu-id="23322-167">Dump Functions</span></span>

<span data-ttu-id="23322-168">為協助針對量副程式進行疑難排解， <xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> 。</span><span class="sxs-lookup"><span data-stu-id="23322-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="23322-169">產生的每個輸出都取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="23322-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="23322-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="23322-170">DumpMachine</span></span>

<span data-ttu-id="23322-171">散發為量子開發工具組一部分的全狀態配量模擬器會以一維複數陣列的形式，將整個量子系統的[wave 函數](https://en.wikipedia.org/wiki/Wave_function)寫入檔案中，其中每個專案都代表測量計算基礎狀態 $ \ket{n} $ 的機率幅度，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $ b_i $ b_1b_0} \{ $ \} 。</span><span class="sxs-lookup"><span data-stu-id="23322-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="23322-172">例如，在只配置兩個 qubits 且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} \ket 的電腦上 {2} ， {10} \end{align} $ $ 呼叫會 <xref:microsoft.quantum.diagnostics.dumpmachine> 產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="23322-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="23322-173">第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="23322-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="23322-174">其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{n} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="23322-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="23322-175">第一列的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="23322-175">In detail for the first row:</span></span>

* <span data-ttu-id="23322-176">**`∣0❭:`** 此資料列對應于 `0` 計算基礎狀態</span><span class="sxs-lookup"><span data-stu-id="23322-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="23322-177">**`0.707107 +  0.000000 i`**：笛卡爾格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="23322-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="23322-178">**` == `**： `equal` 符號會分隔兩個對等的標記法。</span><span class="sxs-lookup"><span data-stu-id="23322-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="23322-179">**`**********  `**：大小的圖形表示，的數目與 `*` 測量此狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="23322-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="23322-180">**`[ 0.500000 ]`**：量值的數值</span><span class="sxs-lookup"><span data-stu-id="23322-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="23322-181">**`    ---`**：振幅階段的圖形標記法（請參閱下列輸出）。</span><span class="sxs-lookup"><span data-stu-id="23322-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="23322-182">**`[ 0.0000 rad ]`**：階段的數值（以弧度為單位）。</span><span class="sxs-lookup"><span data-stu-id="23322-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="23322-183">大小和階段都會以圖形標記法顯示。</span><span class="sxs-lookup"><span data-stu-id="23322-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="23322-184">量值的表示方式很簡單：它會顯示的長條，長條的機率愈大 `*` 。</span><span class="sxs-lookup"><span data-stu-id="23322-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="23322-185">在階段中，我們會根據範圍顯示下列符號來表示角度：</span><span class="sxs-lookup"><span data-stu-id="23322-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="23322-186">下列範例會顯示 `DumpMachine` 一些常見的狀態：</span><span class="sxs-lookup"><span data-stu-id="23322-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="23322-187">Qubit 的識別碼是在執行時間指派，而且不一定會與 qubit 的配置順序或其在 qubit 暫存器內的位置對齊。</span><span class="sxs-lookup"><span data-stu-id="23322-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="23322-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23322-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="23322-189">您可以在程式碼中放入中斷點，並檢查 qubit 變數的值，以在 Visual Studio 中尋找 qubit 識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="23322-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中顯示 qubit 識別碼](~/media/qubit_id.png)
  >
  > <span data-ttu-id="23322-191">索引 on 的 qubit `0` `register2` 具有識別碼 = `3` ，索引的 qubit 具有 `1` 識別碼 = `2` 。</span><span class="sxs-lookup"><span data-stu-id="23322-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="23322-192">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="23322-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="23322-193">您可以使用函式來尋找 qubit 識別碼 <xref:microsoft.quantum.intrinsic.message> ，並在訊息中傳遞 qubit 變數，例如：</span><span class="sxs-lookup"><span data-stu-id="23322-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="23322-194">這可能會產生此輸出：</span><span class="sxs-lookup"><span data-stu-id="23322-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="23322-195">這表示索引 on 的 qubit `0` `register2` 具有識別碼 = `3` ，索引的 qubit 具有 `1` 識別碼 = `2` 。</span><span class="sxs-lookup"><span data-stu-id="23322-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="23322-196">由於 <xref:microsoft.quantum.diagnostics.dumpmachine> 屬於 <xref:microsoft.quantum.diagnostics> 命名空間的一部分，因此您必須加入 `open` 語句來存取它：</span><span class="sxs-lookup"><span data-stu-id="23322-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="23322-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="23322-197">DumpRegister</span></span>

<span data-ttu-id="23322-198"><xref:microsoft.quantum.diagnostics.dumpregister>的運作方式類似 <xref:microsoft.quantum.diagnostics.dumpmachine> ，不同之處在于它也會採用 qubits 陣列，將資訊數量限制為僅與對應的 qubits 相關。</span><span class="sxs-lookup"><span data-stu-id="23322-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="23322-199">如同 <xref:microsoft.quantum.diagnostics.dumpmachine> ，所產生的資訊 <xref:microsoft.quantum.diagnostics.dumpregister> 取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="23322-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="23322-200">對於全狀態的配量模擬器，它會將 wave 函式寫入檔案中，並以與相同格式，由提供的 qubits 所產生之量子子系統的全域階段 <xref:microsoft.quantum.diagnostics.dumpmachine> 。</span><span class="sxs-lookup"><span data-stu-id="23322-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="23322-201">例如，再次使用已配置兩個 qubits 的機器，並在量子 state $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} {2} \ket {10} =-e ^ {-i \ pi/4} （（\frac {1} {\sqrt {2} } \ket {0} -\frac{（1 + i）} \ket） {2} {1} \otimes \frac{-（1 + i）} {\sqrt {2} } \ket {0} ）、\end{align} $ $ 對的呼叫會產生下列 <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` 輸出：</span><span class="sxs-lookup"><span data-stu-id="23322-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="23322-202"><xref:microsoft.quantum.diagnostics.dumpregister>對的呼叫會 `qubit[1]` 產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="23322-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="23322-203">一般來說，與另一個暫存器光子的暫存器的狀態是混合狀態，而不是純狀態。</span><span class="sxs-lookup"><span data-stu-id="23322-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="23322-204">在此情況下，會 <xref:microsoft.quantum.diagnostics.dumpregister> 輸出下列訊息：</span><span class="sxs-lookup"><span data-stu-id="23322-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="23322-205">下列範例會示範如何 <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> 在您的 Q # 程式碼中使用和：</span><span class="sxs-lookup"><span data-stu-id="23322-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="23322-206">偵錯</span><span class="sxs-lookup"><span data-stu-id="23322-206">Debugging</span></span>

<span data-ttu-id="23322-207">在和函 `Assert` 式 `Dump` 和作業之上，Q # 支援標準 Visual Studio 偵錯工具的子集：[設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[逐步執行使用 F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)的程式碼，以及[檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)在模擬器的程式碼執行期間都可以。</span><span class="sxs-lookup"><span data-stu-id="23322-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="23322-208">在 Visual Studio Code 中的偵錯工具會利用 c # 提供的偵錯工具功能，以供 OmniSharp 所支援的 Visual Studio Code 延伸模組，而且需要安裝[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="23322-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
