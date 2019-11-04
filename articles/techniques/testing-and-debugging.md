---
title: 'Q # 技術-測試和調試 |Microsoft Docs'
description: 'Q # 技術-測試和調試'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183483"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="c326b-103">測試和調試</span><span class="sxs-lookup"><span data-stu-id="c326b-103">Testing and Debugging</span></span>

<span data-ttu-id="c326b-104">就像傳統程式設計一樣，要能夠檢查配量程式是否符合預期，以及能夠診斷出不正確的量副程式，是很重要的。</span><span class="sxs-lookup"><span data-stu-id="c326b-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="c326b-105">在本節中，我們將討論 Q # 提供的工具，以測試和偵測量副程式。</span><span class="sxs-lookup"><span data-stu-id="c326b-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="c326b-106">單元測試</span><span class="sxs-lookup"><span data-stu-id="c326b-106">Unit Tests</span></span>

<span data-ttu-id="c326b-107">測試傳統程式的一個常見方法是撰寫稱為「*單元測試*」的小型程式，以在程式庫中執行程式碼，並將其輸出與某些預期的輸出做比較。</span><span class="sxs-lookup"><span data-stu-id="c326b-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="c326b-108">例如，我們可能會想要確保 `Square(2)` 會傳回 `4`，因為我們知道 $ 2 ^ 2 = $4*的先驗*。</span><span class="sxs-lookup"><span data-stu-id="c326b-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="c326b-109">問 # 支援針對量副程式建立單元測試，並可在[xUnit](https://xunit.github.io/)單元測試架構中做為測試執行。</span><span class="sxs-lookup"><span data-stu-id="c326b-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="c326b-110">建立測試專案</span><span class="sxs-lookup"><span data-stu-id="c326b-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="c326b-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c326b-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c326b-112">開啟 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="c326b-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="c326b-113">移至 [`File`] 功能表，然後選取 [`New` > `Project...`]。</span><span class="sxs-lookup"><span data-stu-id="c326b-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="c326b-114">在 [專案範本瀏覽器] 的 [`Installed` > `Visual C#`] 底下，選取 [`Q# Test Project`] 範本。</span><span class="sxs-lookup"><span data-stu-id="c326b-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="c326b-115">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c326b-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c326b-116">從您最愛的命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c326b-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="c326b-117">不論是哪一種情況，您的新專案都會開啟兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="c326b-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="c326b-118">第一個檔案（`Tests.qs`）提供一個方便的位置來定義新的 Q # 單元測試。</span><span class="sxs-lookup"><span data-stu-id="c326b-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="c326b-119">這個檔案一開始會包含一個範例單元測試 `AllocateQubitTest`，它會檢查新配置的 qubit 是否處於 $ \ket{0}$ 狀態，並會列印一則訊息：</span><span class="sxs-lookup"><span data-stu-id="c326b-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="c326b-120">與 `(Unit -> Unit)` 相容 `(Unit => Unit)` 或函式的任何 Q # 作業，都可以當做單元測試來執行。</span><span class="sxs-lookup"><span data-stu-id="c326b-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="c326b-121">第二個檔案（`TestSuiteRunner.cs` 包含探索並執行 Q # 單元測試的方法）。</span><span class="sxs-lookup"><span data-stu-id="c326b-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="c326b-122">這是 `TestTarget` 批註 `OperationDriver` 屬性的方法。</span><span class="sxs-lookup"><span data-stu-id="c326b-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="c326b-123">`OperationDriver` 屬性是 Xunit 延伸模組程式庫 Xunit 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c326b-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="c326b-124">單元測試架構會針對其探索到的每個 Q # 單元測試，呼叫 `TestTarget` 方法。</span><span class="sxs-lookup"><span data-stu-id="c326b-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="c326b-125">架構會透過 `op` 引數，將單元測試描述傳遞給方法。</span><span class="sxs-lookup"><span data-stu-id="c326b-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="c326b-126">下列程式程式碼：</span><span class="sxs-lookup"><span data-stu-id="c326b-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="c326b-127">在 `QuantumSimulator`上執行單元測試。</span><span class="sxs-lookup"><span data-stu-id="c326b-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="c326b-128">根據預設，單元測試探索機制會尋找符合下列屬性的所有 Q # 函數或相容類型的作業：</span><span class="sxs-lookup"><span data-stu-id="c326b-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="c326b-129">位於與 `OperationDriver` 屬性標注之方法相同的元件中。</span><span class="sxs-lookup"><span data-stu-id="c326b-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="c326b-130">位於與 `OperationDriver` 屬性標注之方法相同的命名空間中。</span><span class="sxs-lookup"><span data-stu-id="c326b-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="c326b-131">名稱結尾為 `Test`。</span><span class="sxs-lookup"><span data-stu-id="c326b-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="c326b-132">您可以使用 `OperationDriver` 屬性的選擇性參數來設定元件、命名空間和單元測試函式和作業的尾碼：</span><span class="sxs-lookup"><span data-stu-id="c326b-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="c326b-133">`AssemblyName` 參數會設定要在其中搜尋測試的元件名稱。</span><span class="sxs-lookup"><span data-stu-id="c326b-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="c326b-134">`TestNamespace` 參數會設定要在其中搜尋測試的命名空間名稱。</span><span class="sxs-lookup"><span data-stu-id="c326b-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="c326b-135">`Suffix` 設定視為單元測試之作業或函數名稱的尾碼。</span><span class="sxs-lookup"><span data-stu-id="c326b-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="c326b-136">此外，`TestCasePrefix` 選擇性參數可讓您設定測試案例名稱的前置詞。</span><span class="sxs-lookup"><span data-stu-id="c326b-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="c326b-137">作業名稱前面的前置詞會出現在測試案例清單中。</span><span class="sxs-lookup"><span data-stu-id="c326b-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="c326b-138">例如，`TestCasePrefix = "QSim:"` 會導致 `AllocateQubitTest` 在找到的測試清單中顯示為 `QSim:AllocateQubitTest`。</span><span class="sxs-lookup"><span data-stu-id="c326b-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="c326b-139">這可能有助於表示用來執行測試的模擬器。</span><span class="sxs-lookup"><span data-stu-id="c326b-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="c326b-140">執行 Q # 單元測試</span><span class="sxs-lookup"><span data-stu-id="c326b-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="c326b-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c326b-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c326b-142">如果是一次的每一解決方案設定，請移至 `Test` 功能表，然後選取 `Test Settings` > `Default Processor Architecture` > `X64`。</span><span class="sxs-lookup"><span data-stu-id="c326b-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="c326b-143">Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項（`.suo`）檔案中。</span><span class="sxs-lookup"><span data-stu-id="c326b-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="c326b-144">如果您刪除此檔案，則需要選取 [`X64`] 做為您的處理器架構。</span><span class="sxs-lookup"><span data-stu-id="c326b-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="c326b-145">建立專案，移至 [`Test`] 功能表，然後選取 [`Windows` > `Test Explorer`]。</span><span class="sxs-lookup"><span data-stu-id="c326b-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="c326b-146">`AllocateQubitTest` 會顯示在 `Not Run Tests` 群組中的測試清單中。</span><span class="sxs-lookup"><span data-stu-id="c326b-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="c326b-147">選取 `Run All` 或執行此個別測試，它應該會通過！</span><span class="sxs-lookup"><span data-stu-id="c326b-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="c326b-148">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c326b-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c326b-149">若要執行測試，請流覽至專案資料夾（包含 `Tests.csproj`的資料夾），然後執行命令：</span><span class="sxs-lookup"><span data-stu-id="c326b-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="c326b-150">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="c326b-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="c326b-151">記錄和判斷提示</span><span class="sxs-lookup"><span data-stu-id="c326b-151">Logging and Assertions</span></span>

<span data-ttu-id="c326b-152">問 # 中的函式沒有副作用的其中一個重要結果，就是執行某個函式的輸出類型為空元組 `()` 的任何效果，都不能從 Q # 程式中觀察到。</span><span class="sxs-lookup"><span data-stu-id="c326b-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="c326b-153">也就是說，目的電腦可以選擇不執行任何會傳回 `()` 的函式，保證此省略不會修改任何下列 Q 號碼程式碼的行為。</span><span class="sxs-lookup"><span data-stu-id="c326b-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="c326b-154">這會讓函式傳回 `()` 有用的工具，將判斷提示和偵錯工具內嵌到 Q # 程式中。</span><span class="sxs-lookup"><span data-stu-id="c326b-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="c326b-155">記錄</span><span class="sxs-lookup"><span data-stu-id="c326b-155">Logging</span></span>

<span data-ttu-id="c326b-156">內建函式 <xref:microsoft.quantum.intrinsic.message> 具有類型 `(String -> Unit)`，並可讓您建立診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="c326b-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="c326b-157">`QuantumSimulator` 的 `onLog` 動作可以用來定義當問 # 程式碼呼叫 `Message`時所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="c326b-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="c326b-158">根據預設，記錄的訊息會列印到標準輸出。</span><span class="sxs-lookup"><span data-stu-id="c326b-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="c326b-159">定義單元測試套件時，已記錄的訊息可以導向至測試輸出。</span><span class="sxs-lookup"><span data-stu-id="c326b-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="c326b-160">從 Q # 測試專案範本建立專案時，會針對套件預先設定此重新導向，並根據預設建立此重新導向，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c326b-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="c326b-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c326b-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c326b-162">在測試瀏覽器中執行測試並按一下測試之後，會出現一個面板，其中包含測試執行的相關資訊：通過/失敗狀態、經過時間和「輸出」連結。</span><span class="sxs-lookup"><span data-stu-id="c326b-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="c326b-163">如果您按一下 [輸出] 連結，測試輸出將會在新視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="c326b-163">If you click the "Output" link, test output will open in a new window.</span></span>

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="c326b-165">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c326b-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c326b-166">`dotnet test`，會將每個測試的通過/失敗狀態列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="c326b-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="c326b-167">針對失敗的測試，記錄為上述 `output.WriteLine(msg)` 呼叫結果的輸出也會列印到主控台，以協助診斷失敗。</span><span class="sxs-lookup"><span data-stu-id="c326b-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="c326b-168">聲明</span><span class="sxs-lookup"><span data-stu-id="c326b-168">Assertions</span></span>

<span data-ttu-id="c326b-169">相同的邏輯也可以套用到執行判斷提示。</span><span class="sxs-lookup"><span data-stu-id="c326b-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="c326b-170">讓我們來看一個簡單的範例：</span><span class="sxs-lookup"><span data-stu-id="c326b-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="c326b-171">在這裡，關鍵字 `fail` 表示計算不應繼續，而是在執行 Q # 程式的目的電腦中引發例外狀況。</span><span class="sxs-lookup"><span data-stu-id="c326b-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="c326b-172">根據定義，無法從 Q # 中觀察到這種錯誤，因為在到達 `fail` 語句之後，不會再執行 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="c326b-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="c326b-173">因此，如果我們繼續呼叫 `AssertPositive`，我們可以確保其輸入是正數。</span><span class="sxs-lookup"><span data-stu-id="c326b-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="c326b-174">根據這些想法，[序言](xref:microsoft.quantum.libraries.standard.prelude)提供兩個特別有用的判斷提示，<xref:microsoft.quantum.intrinsic.assert>，並 <xref:microsoft.quantum.intrinsic.assertprob> 模型化 as 作業放入 `()`。</span><span class="sxs-lookup"><span data-stu-id="c326b-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="c326b-175">這些判斷提示各自採用 Pauli 運算子來描述特定測量量、要執行測量的量子暫存器，以及假設結果。</span><span class="sxs-lookup"><span data-stu-id="c326b-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="c326b-176">在模擬使用的目的機器上，我們不會受限於「[無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)，而且可以執行這類測量，而不會干擾傳遞至這類判斷提示的暫存器。</span><span class="sxs-lookup"><span data-stu-id="c326b-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="c326b-177">模擬器之後就可以類似于上述的 `AssertPositive` 函式，如果在實際情況下不會觀察到假設的結果，就會中止計算：</span><span class="sxs-lookup"><span data-stu-id="c326b-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="c326b-178">在實體量子硬體上，如果沒有複製定理可防止檢查配量狀態，`Assert` 和 `AssertProb` 作業只會傳回 `()`，而不會有任何其他效果。</span><span class="sxs-lookup"><span data-stu-id="c326b-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="c326b-179"><xref:microsoft.quantum.diagnostics> 命名空間提供 `Assert` 系列的多項功能，可讓我們檢查更先進的條件。</span><span class="sxs-lookup"><span data-stu-id="c326b-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="c326b-180">傾印函式</span><span class="sxs-lookup"><span data-stu-id="c326b-180">Dump Functions</span></span>

<span data-ttu-id="c326b-181">為了協助針對量副程式進行疑難排解，<xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister>。</span><span class="sxs-lookup"><span data-stu-id="c326b-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="c326b-182">產生的每個輸出都取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="c326b-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="c326b-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="c326b-183">DumpMachine</span></span>

<span data-ttu-id="c326b-184">散發為量子開發工具組一部分的全狀態配量模擬器會以一維複數陣列的形式，將整個量子系統的[wave](https://en.wikipedia.org/wiki/Wave_function)函式寫入檔案中，其中每個元素都代表的振幅測量計算基礎狀態 $ \ket{n} $ 的機率，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $\{的 b_1b_0} $ b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="c326b-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="c326b-185">例如，在只配置兩個 qubits 且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10}中的電腦上，\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpmachine> 會產生此輸出:</span><span class="sxs-lookup"><span data-stu-id="c326b-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c326b-186">第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="c326b-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="c326b-187">其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{n} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="c326b-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="c326b-188">第一列的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c326b-188">In detail for the first row:</span></span>

* <span data-ttu-id="c326b-189">**`∣0❭:`** 此資料列對應至 `0` 計算基礎狀態</span><span class="sxs-lookup"><span data-stu-id="c326b-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="c326b-190">**`0.707107 +  0.000000 i`** ：以笛卡兒格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="c326b-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="c326b-191">**` == `** ： `equal` sign seperates 兩個對等的標記法。</span><span class="sxs-lookup"><span data-stu-id="c326b-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="c326b-192">**`**********  `** ：大小的圖形表示，`*` 的數目與測量此狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="c326b-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="c326b-193">**`[ 0.500000 ]`** ：量值的數值</span><span class="sxs-lookup"><span data-stu-id="c326b-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="c326b-194">**`    ---`** ：波幅階段的圖形標記法（請參閱下文）。</span><span class="sxs-lookup"><span data-stu-id="c326b-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="c326b-195">**`[ 0.0000 rad ]`** ：階段的數值（以弧度為單位）。</span><span class="sxs-lookup"><span data-stu-id="c326b-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="c326b-196">大小和階段都會以圖形標記法顯示。</span><span class="sxs-lookup"><span data-stu-id="c326b-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="c326b-197">量值的表示方式很簡單：它會顯示 `*`的長條，長條的機率愈大。</span><span class="sxs-lookup"><span data-stu-id="c326b-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="c326b-198">在階段中，我們會根據範圍顯示下列符號來表示角度：</span><span class="sxs-lookup"><span data-stu-id="c326b-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="c326b-199">下列範例顯示一些常見狀態的 `DumpMachine`：</span><span class="sxs-lookup"><span data-stu-id="c326b-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="c326b-200">Qubit 的識別碼會在執行時間指派，而且不一定會與 qubit 的配置順序或其在 qubit 暫存器內的位置對齊。</span><span class="sxs-lookup"><span data-stu-id="c326b-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="c326b-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c326b-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="c326b-202">您可以在程式碼中放入中斷點，並檢查 qubit 變數的值，藉以找出 Visual Studio 中的 qubit 識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="c326b-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中顯示 qubit 識別碼](~/media/qubit_id.png)
  >
  > <span data-ttu-id="c326b-204">`register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。</span><span class="sxs-lookup"><span data-stu-id="c326b-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="c326b-205">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c326b-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="c326b-206">您可以使用 <xref:microsoft.quantum.intrinsic.message> 函式並傳遞訊息中的 qubit 變數，來找出 qubit 識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="c326b-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="c326b-207">這可能會產生此輸出：</span><span class="sxs-lookup"><span data-stu-id="c326b-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="c326b-208">這表示 `register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。</span><span class="sxs-lookup"><span data-stu-id="c326b-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="c326b-209"><xref:microsoft.quantum.diagnostics.dumpmachine> 是 <xref:microsoft.quantum.diagnostics> 命名空間的一部分，因此若要使用它，您必須加入 `open` 語句：</span><span class="sxs-lookup"><span data-stu-id="c326b-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="c326b-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="c326b-210">DumpRegister</span></span>

<span data-ttu-id="c326b-211"><xref:microsoft.quantum.diagnostics.dumpregister> 的運作方式類似 <xref:microsoft.quantum.diagnostics.dumpmachine>，不同之處在于它也會採用 qubits 陣列，將資訊數量限制為僅與對應的 qubits 相關。</span><span class="sxs-lookup"><span data-stu-id="c326b-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="c326b-212">如同 <xref:microsoft.quantum.diagnostics.dumpmachine>，<xref:microsoft.quantum.diagnostics.dumpregister> 產生的資訊取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="c326b-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="c326b-213">對於全狀態的配量模擬器，它會將 wave 函式寫入檔案中，並以 <xref:microsoft.quantum.diagnostics.dumpmachine>的相同格式，由提供的 qubits 所產生的量子子系統的全域階段來運作。</span><span class="sxs-lookup"><span data-stu-id="c326b-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="c326b-214">例如，請再次將只有兩個 qubits 配置的機器，並在量子 state $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10} =-e ^ {-i \ pi/4} （（\frac{1}{\sqrt{2}} \ket{0}-\frac{（1 + i）}{2} \ket{1}） \otimes \frac{-（1 + i）} {\sqrt{2}} \ket{0}），\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpregister> 以進行 `qubit[0]` 會產生此輸出：</span><span class="sxs-lookup"><span data-stu-id="c326b-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c326b-215">而呼叫 `qubit[1]` 的 <xref:microsoft.quantum.diagnostics.dumpregister> 會產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c326b-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="c326b-216">一般來說，與另一個暫存器光子的暫存器的狀態是混合狀態，而不是純狀態。</span><span class="sxs-lookup"><span data-stu-id="c326b-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="c326b-217">在此情況下，<xref:microsoft.quantum.diagnostics.dumpregister> 會輸出下列訊息：</span><span class="sxs-lookup"><span data-stu-id="c326b-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="c326b-218">下列範例會示範如何在您的 Q # 程式碼中使用 <xref:microsoft.quantum.diagnostics.dumpregister> 和 <xref:microsoft.quantum.diagnostics.dumpmachine>：</span><span class="sxs-lookup"><span data-stu-id="c326b-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="c326b-219">偵錯</span><span class="sxs-lookup"><span data-stu-id="c326b-219">Debugging</span></span>

<span data-ttu-id="c326b-220">在 `Assert` 和 `Dump` 函式和作業之上，Q # 支援標準 Visual Studio 偵錯工具的子集：[設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)及[檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)在模擬器上執行程式碼期間都可以。</span><span class="sxs-lookup"><span data-stu-id="c326b-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="c326b-221">尚不支援在 Visual Studio Code 中進行調試。</span><span class="sxs-lookup"><span data-stu-id="c326b-221">Debugging in Visual Studio Code is not yet supported.</span></span>

