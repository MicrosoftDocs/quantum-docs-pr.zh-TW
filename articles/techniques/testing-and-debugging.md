---
title: '測試和調試-Q # 技術 |Microsoft Docs'
description: '測試和調試-Q # 技術'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: cfc71f08be0f190d9f5f4a48796e3d0ad06d6107
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820108"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="55316-103">測試和調試</span><span class="sxs-lookup"><span data-stu-id="55316-103">Testing and Debugging</span></span>

<span data-ttu-id="55316-104">就像傳統程式設計一樣，要能夠檢查配量程式是否符合預期，以及能夠診斷出不正確的量副程式，是很重要的。</span><span class="sxs-lookup"><span data-stu-id="55316-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="55316-105">在本節中，我們將討論 Q # 提供的工具，以測試和偵測量副程式。</span><span class="sxs-lookup"><span data-stu-id="55316-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="55316-106">單元測試</span><span class="sxs-lookup"><span data-stu-id="55316-106">Unit Tests</span></span>

<span data-ttu-id="55316-107">測試傳統程式的一個常見方法是撰寫稱為「*單元測試*」的小型程式，以在程式庫中執行程式碼，並將其輸出與某些預期的輸出做比較。</span><span class="sxs-lookup"><span data-stu-id="55316-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="55316-108">例如，我們可能會想要確保 `Square(2)` 會傳回 `4`，因為我們知道 $ 2 ^ 2 = $4*的先驗*。</span><span class="sxs-lookup"><span data-stu-id="55316-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="55316-109">問 # 支援針對量副程式建立單元測試，並可在[xUnit](https://xunit.github.io/)單元測試架構中做為測試執行。</span><span class="sxs-lookup"><span data-stu-id="55316-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="55316-110">建立測試專案</span><span class="sxs-lookup"><span data-stu-id="55316-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="55316-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="55316-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="55316-112">開啟 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="55316-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="55316-113">移至 [`File`] 功能表，然後選取 [`New` > `Project...`]。</span><span class="sxs-lookup"><span data-stu-id="55316-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="55316-114">在右上角，搜尋 [`Q#`]，然後選取 [`Q# Test Project`] 範本。</span><span class="sxs-lookup"><span data-stu-id="55316-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="55316-115">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="55316-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="55316-116">從您最愛的命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="55316-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="55316-117">您的新專案將會有單一檔案 `Tests.qs`，這會提供一個方便的位置來定義新的 Q # 單元測試。</span><span class="sxs-lookup"><span data-stu-id="55316-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="55316-118">這個檔案一開始會包含一個範例單元測試 `AllocateQubit`，它會檢查新配置的 qubit 是否處於 $ \ket{0}$ 狀態，並會列印一則訊息：</span><span class="sxs-lookup"><span data-stu-id="55316-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="55316-119">：新增：接受 `Unit` 類型之引數的任何 Q # 作業或函式，並可透過 `@Test("...")` 屬性將 `Unit` 標記為單元測試。</span><span class="sxs-lookup"><span data-stu-id="55316-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="55316-120">上述 `"QuantumSimulator"` 屬性（attribute）的引數會指定要執行測試的目標。</span><span class="sxs-lookup"><span data-stu-id="55316-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="55316-121">單一測試可以在多個目標上執行。</span><span class="sxs-lookup"><span data-stu-id="55316-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="55316-122">例如，`@Test("ResourcesEstimator")` `AllocateQubit`上新增屬性。</span><span class="sxs-lookup"><span data-stu-id="55316-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="55316-123">儲存檔案並執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="55316-123">Save the file and execute all tests.</span></span> <span data-ttu-id="55316-124">現在應該有兩個單元測試，一個在 QuantumSimulator 上執行 AllocateQubit，另一個在 ResourceEstimator 中執行。</span><span class="sxs-lookup"><span data-stu-id="55316-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="55316-125">Q # 編譯器會將內建目標 "QuantumSimulator"、"ToffoliSimulator" 和 "ResourcesEstimator" 辨識為適用于單元測試的有效執行目標。</span><span class="sxs-lookup"><span data-stu-id="55316-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="55316-126">也可以指定任何完整名稱，以定義自訂的執行目標。</span><span class="sxs-lookup"><span data-stu-id="55316-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="55316-127">執行 Q # 單元測試</span><span class="sxs-lookup"><span data-stu-id="55316-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="55316-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="55316-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="55316-129">如果是一次的每一解決方案設定，請移至 `Test` 功能表，然後選取 `Test Settings` > `Default Processor Architecture` > `X64`。</span><span class="sxs-lookup"><span data-stu-id="55316-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="55316-130">Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項（`.suo`）檔案中。</span><span class="sxs-lookup"><span data-stu-id="55316-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="55316-131">如果您刪除此檔案，則需要選取 [`X64`] 做為您的處理器架構。</span><span class="sxs-lookup"><span data-stu-id="55316-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="55316-132">建立專案，移至 [`Test`] 功能表，然後選取 [`Windows` > `Test Explorer`]。</span><span class="sxs-lookup"><span data-stu-id="55316-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="55316-133">`AllocateQubit` 會顯示在 `Not Run Tests` 群組中的測試清單中。</span><span class="sxs-lookup"><span data-stu-id="55316-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="55316-134">選取 `Run All` 或執行此個別測試，它應該會通過！</span><span class="sxs-lookup"><span data-stu-id="55316-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="55316-135">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="55316-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="55316-136">若要執行測試，請流覽至專案資料夾（包含 `Tests.csproj`的資料夾），然後執行命令：</span><span class="sxs-lookup"><span data-stu-id="55316-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="55316-137">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="55316-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="55316-138">單元測試可以根據其名稱和/或執行目標來進行篩選：</span><span class="sxs-lookup"><span data-stu-id="55316-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="55316-139">內建函式 <xref:microsoft.quantum.intrinsic.message> 具有類型 `(String -> Unit)`，並可讓您建立診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="55316-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="55316-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="55316-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="55316-141">在測試瀏覽器中執行測試並按一下測試之後，會出現一個面板，其中包含測試執行的相關資訊：通過/失敗狀態、經過時間和「輸出」連結。</span><span class="sxs-lookup"><span data-stu-id="55316-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="55316-142">如果您按一下 [輸出] 連結，測試輸出將會在新視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="55316-142">If you click the "Output" link, test output will open in a new window.</span></span>

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="55316-144">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="55316-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="55316-145">`dotnet test`，會將每個測試的通過/失敗狀態列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="55316-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="55316-146">對於失敗的測試，輸出也會列印到主控台，以協助診斷失敗。</span><span class="sxs-lookup"><span data-stu-id="55316-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="assertions"></a><span data-ttu-id="55316-147">聲明</span><span class="sxs-lookup"><span data-stu-id="55316-147">Assertions</span></span>

<span data-ttu-id="55316-148">因為 Q # 中的函式沒有_邏輯_副作用，所以執行其輸出類型為空元組的函式的任何_其他類型_`()` 永遠不會從 Q # 程式中觀察到。</span><span class="sxs-lookup"><span data-stu-id="55316-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="55316-149">也就是說，目的電腦可以選擇不執行任何會傳回 `()` 的函式，保證此省略不會修改任何下列 Q 號碼程式碼的行為。</span><span class="sxs-lookup"><span data-stu-id="55316-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="55316-150">這會讓函式傳回 `()` 有用的工具，將判斷提示和偵錯工具內嵌到 Q # 程式中。</span><span class="sxs-lookup"><span data-stu-id="55316-150">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="55316-151">相同的邏輯也可以套用到執行判斷提示。</span><span class="sxs-lookup"><span data-stu-id="55316-151">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="55316-152">讓我們來看一個簡單的範例：</span><span class="sxs-lookup"><span data-stu-id="55316-152">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="55316-153">在這裡，關鍵字 `fail` 表示計算不應繼續，而是在執行 Q # 程式的目的電腦中引發例外狀況。</span><span class="sxs-lookup"><span data-stu-id="55316-153">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="55316-154">根據定義，無法從 Q # 中觀察到這種錯誤，因為在到達 `fail` 語句之後，不會再執行 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="55316-154">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="55316-155">因此，如果我們繼續呼叫 `AssertPositive`，我們可以確保其輸入是正數。</span><span class="sxs-lookup"><span data-stu-id="55316-155">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="55316-156">根據這些想法，[序言](xref:microsoft.quantum.libraries.standard.prelude)提供兩個特別有用的判斷提示，<xref:microsoft.quantum.intrinsic.assert>，並 <xref:microsoft.quantum.intrinsic.assertprob> 模型化 as 作業放入 `()`。</span><span class="sxs-lookup"><span data-stu-id="55316-156">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="55316-157">這些判斷提示各自採用 Pauli 運算子來描述特定測量量、要執行測量的量子暫存器，以及假設結果。</span><span class="sxs-lookup"><span data-stu-id="55316-157">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="55316-158">在模擬使用的目的機器上，我們不會受限於「[無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)，而且可以執行這類測量，而不會干擾傳遞至這類判斷提示的暫存器。</span><span class="sxs-lookup"><span data-stu-id="55316-158">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="55316-159">模擬器之後就可以類似于上述的 `AssertPositive` 函式，如果在實際情況下不會觀察到假設的結果，就會中止計算：</span><span class="sxs-lookup"><span data-stu-id="55316-159">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="55316-160">在實體量子硬體上，如果沒有複製定理可防止檢查配量狀態，`Assert` 和 `AssertProb` 作業只會傳回 `()`，而不會有任何其他效果。</span><span class="sxs-lookup"><span data-stu-id="55316-160">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="55316-161"><xref:microsoft.quantum.diagnostics> 命名空間提供 `Assert` 系列的多項功能，可讓我們檢查更先進的條件。</span><span class="sxs-lookup"><span data-stu-id="55316-161">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="55316-162">傾印函式</span><span class="sxs-lookup"><span data-stu-id="55316-162">Dump Functions</span></span>

<span data-ttu-id="55316-163">為了協助針對量副程式進行疑難排解，<xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister>。</span><span class="sxs-lookup"><span data-stu-id="55316-163">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="55316-164">產生的每個輸出都取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="55316-164">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="55316-165">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="55316-165">DumpMachine</span></span>

<span data-ttu-id="55316-166">散發為量子開發工具組一部分的全狀態配量模擬器會以一維複數陣列的形式，將整個量子系統的[wave 函數](https://en.wikipedia.org/wiki/Wave_function)寫入檔案中，其中每個專案都代表測量計算基礎狀態 $ \ket{n} $ 的機率幅度，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $\{的 b_1b_0} $ b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="55316-166">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="55316-167">例如，在只配置兩個 qubits 且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10}中的電腦上，\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpmachine> 會產生此輸出：</span><span class="sxs-lookup"><span data-stu-id="55316-167">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="55316-168">第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="55316-168">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="55316-169">其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{n} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="55316-169">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="55316-170">第一列的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="55316-170">In detail for the first row:</span></span>

* <span data-ttu-id="55316-171">**`∣0❭:`** 此資料列對應至 `0` 計算基礎狀態</span><span class="sxs-lookup"><span data-stu-id="55316-171">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="55316-172">**`0.707107 +  0.000000 i`** ：以笛卡兒格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="55316-172">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="55316-173">**` == `** ： `equal` sign seperates 兩個對等的標記法。</span><span class="sxs-lookup"><span data-stu-id="55316-173">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="55316-174">**`**********  `** ：大小的圖形表示，`*` 的數目與測量此狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="55316-174">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="55316-175">**`[ 0.500000 ]`** ：量值的數值</span><span class="sxs-lookup"><span data-stu-id="55316-175">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="55316-176">**`    ---`** ：波幅階段的圖形標記法（請參閱下文）。</span><span class="sxs-lookup"><span data-stu-id="55316-176">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="55316-177">**`[ 0.0000 rad ]`** ：階段的數值（以弧度為單位）。</span><span class="sxs-lookup"><span data-stu-id="55316-177">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="55316-178">大小和階段都會以圖形標記法顯示。</span><span class="sxs-lookup"><span data-stu-id="55316-178">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="55316-179">量值的表示方式很簡單：它會顯示 `*`的長條，長條的機率愈大。</span><span class="sxs-lookup"><span data-stu-id="55316-179">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="55316-180">在階段中，我們會根據範圍顯示下列符號來表示角度：</span><span class="sxs-lookup"><span data-stu-id="55316-180">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="55316-181">下列範例顯示一些常見狀態的 `DumpMachine`：</span><span class="sxs-lookup"><span data-stu-id="55316-181">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="55316-182">Qubit 的識別碼會在執行時間指派，而且不一定會與 qubit 的配置順序或其在 qubit 暫存器內的位置對齊。</span><span class="sxs-lookup"><span data-stu-id="55316-182">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="55316-183">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="55316-183">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="55316-184">您可以在程式碼中放入中斷點，並檢查 qubit 變數的值，藉以找出 Visual Studio 中的 qubit 識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="55316-184">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中顯示 qubit 識別碼](~/media/qubit_id.png)
  >
  > <span data-ttu-id="55316-186">`register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。</span><span class="sxs-lookup"><span data-stu-id="55316-186">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="55316-187">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="55316-187">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="55316-188">您可以使用 <xref:microsoft.quantum.intrinsic.message> 函式並傳遞訊息中的 qubit 變數，來找出 qubit 識別碼，例如：</span><span class="sxs-lookup"><span data-stu-id="55316-188">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="55316-189">這可能會產生此輸出：</span><span class="sxs-lookup"><span data-stu-id="55316-189">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="55316-190">這表示 `register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。</span><span class="sxs-lookup"><span data-stu-id="55316-190">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="55316-191"><xref:microsoft.quantum.diagnostics.dumpmachine> 是 <xref:microsoft.quantum.diagnostics> 命名空間的一部分，因此若要使用它，您必須加入 `open` 語句：</span><span class="sxs-lookup"><span data-stu-id="55316-191"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="55316-192">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="55316-192">DumpRegister</span></span>

<span data-ttu-id="55316-193"><xref:microsoft.quantum.diagnostics.dumpregister> 的運作方式類似 <xref:microsoft.quantum.diagnostics.dumpmachine>，不同之處在于它也會採用 qubits 陣列，將資訊數量限制為僅與對應的 qubits 相關。</span><span class="sxs-lookup"><span data-stu-id="55316-193"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="55316-194">如同 <xref:microsoft.quantum.diagnostics.dumpmachine>，<xref:microsoft.quantum.diagnostics.dumpregister> 產生的資訊取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="55316-194">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="55316-195">對於全狀態的配量模擬器，它會將 wave 函式寫入檔案中，並以 <xref:microsoft.quantum.diagnostics.dumpmachine>的相同格式，由提供的 qubits 所產生的量子子系統的全域階段來運作。</span><span class="sxs-lookup"><span data-stu-id="55316-195">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="55316-196">例如，請再次將只有兩個 qubits 配置的機器，並在量子 state $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10} =-e ^ {-i \ pi/4} （（\frac{1}{\sqrt{2}} \ket{0}-\frac{（1 + i）}{2} \ket{1}） \otimes \frac{-（1 + i）} {\sqrt{2}} \ket{0}），\end{align} $ $ 呼叫 `qubit[0]` 的 <xref:microsoft.quantum.diagnostics.dumpregister> 會產生此輸出:</span><span class="sxs-lookup"><span data-stu-id="55316-196">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="55316-197">而呼叫 `qubit[1]` 的 <xref:microsoft.quantum.diagnostics.dumpregister> 會產生下列輸出：</span><span class="sxs-lookup"><span data-stu-id="55316-197">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="55316-198">一般來說，與另一個暫存器光子的暫存器的狀態是混合狀態，而不是純狀態。</span><span class="sxs-lookup"><span data-stu-id="55316-198">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="55316-199">在此情況下，<xref:microsoft.quantum.diagnostics.dumpregister> 會輸出下列訊息：</span><span class="sxs-lookup"><span data-stu-id="55316-199">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="55316-200">下列範例會示範如何在您的 Q # 程式碼中使用 <xref:microsoft.quantum.diagnostics.dumpregister> 和 <xref:microsoft.quantum.diagnostics.dumpmachine>：</span><span class="sxs-lookup"><span data-stu-id="55316-200">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="55316-201">偵錯</span><span class="sxs-lookup"><span data-stu-id="55316-201">Debugging</span></span>

<span data-ttu-id="55316-202">在 `Assert` 和 `Dump` 函式和作業之上，Q # 支援標準 Visual Studio 偵錯工具的子集：[設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)及[檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)，都可以在模擬器的程式碼執行期間進行。</span><span class="sxs-lookup"><span data-stu-id="55316-202">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="55316-203">在 Visual Studio Code 中的偵錯工具會利用由 OmniSharp C#提供的 Visual Studio Code 擴充功能所提供的偵錯工具，而且需要安裝[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="55316-203">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
