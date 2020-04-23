---
title: 測試並除錯 Q# 程式
description: 瞭解如何使用單元測試、事實和斷言以及轉儲函數來測試和調試量子程式。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030577"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="6135c-103">測試和偵錯</span><span class="sxs-lookup"><span data-stu-id="6135c-103">Testing and Debugging</span></span>

<span data-ttu-id="6135c-104">與經典程式設計一樣,必須能夠檢查量子程式是否按預期操作,並能夠診斷不正確的量子程式。</span><span class="sxs-lookup"><span data-stu-id="6135c-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="6135c-105">在本節中,我們將介紹 Q# 提供的用於測試和調試量子程式的工具。</span><span class="sxs-lookup"><span data-stu-id="6135c-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="6135c-106">單元測試</span><span class="sxs-lookup"><span data-stu-id="6135c-106">Unit Tests</span></span>

<span data-ttu-id="6135c-107">測試經典程式的一種常見方法是編寫稱為*單元測試*的小程式,這些程式在庫中運行代碼,並將其輸出與一些預期輸出進行比較。</span><span class="sxs-lookup"><span data-stu-id="6135c-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="6135c-108">例如,我們可能希望確保`Square(2)``4`返回 ,因為我們知道*先驗*的 $2 我們要 2 我們要 2 = 4$。</span><span class="sxs-lookup"><span data-stu-id="6135c-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="6135c-109">Q# 支援為量子程式創建單元測試,可在[xUnit](https://xunit.github.io/)單元測試框架中作為測試執行。</span><span class="sxs-lookup"><span data-stu-id="6135c-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="6135c-110">建立測試項目</span><span class="sxs-lookup"><span data-stu-id="6135c-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6135c-111">視覺工作室 2019</span><span class="sxs-lookup"><span data-stu-id="6135c-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6135c-112">開啟 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="6135c-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="6135c-113">跳到選單並`File``New` > `Project...`選擇 。</span><span class="sxs-lookup"><span data-stu-id="6135c-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="6135c-114">在右上角,搜索`Q#`,然後`Q# Test Project`選擇 範本。</span><span class="sxs-lookup"><span data-stu-id="6135c-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6135c-115">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6135c-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6135c-116">從您最喜愛的命令列中,執行以下指令:</span><span class="sxs-lookup"><span data-stu-id="6135c-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="6135c-117">您的新專案將有一個檔`Tests.qs`,這為定義新的 Q# 單元測試提供了一個方便的位置。</span><span class="sxs-lookup"><span data-stu-id="6135c-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="6135c-118">最初,此檔包含一個範例單元`AllocateQubit`測試,該測試檢查新分配的 qubit{0}是否處於 $ket $ 狀態並列印訊息:</span><span class="sxs-lookup"><span data-stu-id="6135c-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="6135c-119">任何採用`Unit`類型`Unit`和返回 參數的 Q# 操作`@Test("...")`或函數都可以通過 屬性標記為單元測試。</span><span class="sxs-lookup"><span data-stu-id="6135c-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="6135c-120">`"QuantumSimulator"`上面該屬性的參數指定執行測試的目標。</span><span class="sxs-lookup"><span data-stu-id="6135c-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="6135c-121">可以在多個目標上執行單個測試。</span><span class="sxs-lookup"><span data-stu-id="6135c-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="6135c-122">例如,在上`@Test("ResourcesEstimator")``AllocateQubit`添加一個屬性。</span><span class="sxs-lookup"><span data-stu-id="6135c-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="6135c-123">保存檔並執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="6135c-123">Save the file and execute all tests.</span></span> <span data-ttu-id="6135c-124">現在應該有兩個單元測試,一個在昆騰模擬器上執行分配Qubit,另一個在資源估計器中執行。</span><span class="sxs-lookup"><span data-stu-id="6135c-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="6135c-125">Q# 編譯器將內置目標"量子模擬器"、"Toffoli模擬器"和"資源估計器"識別為單元測試的有效執行目標。</span><span class="sxs-lookup"><span data-stu-id="6135c-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="6135c-126">還可以指定任何完全限定的名稱來定義自定義執行目標。</span><span class="sxs-lookup"><span data-stu-id="6135c-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="6135c-127">執行 Q# 單元測試</span><span class="sxs-lookup"><span data-stu-id="6135c-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6135c-128">視覺工作室 2019</span><span class="sxs-lookup"><span data-stu-id="6135c-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6135c-129">作為一次性`Test`每個解決方案設定,轉到選單並`Test Settings` > `Default Processor Architecture` > `X64`選擇 。</span><span class="sxs-lookup"><span data-stu-id="6135c-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="6135c-130">Visual Studio 的預設處理器架構結構設定存儲在每個解決方案的`.suo`解決方案選項 ( ) 檔案中。</span><span class="sxs-lookup"><span data-stu-id="6135c-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="6135c-131">如果刪除此檔,則需要再次選擇`X64`作為處理器體系結構。</span><span class="sxs-lookup"><span data-stu-id="6135c-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="6135c-132">產生`Test`項目,轉到選單並選擇`Windows` > `Test Explorer`。</span><span class="sxs-lookup"><span data-stu-id="6135c-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="6135c-133">`AllocateQubit`將顯示在`Not Run Tests`組中的測試清單中。</span><span class="sxs-lookup"><span data-stu-id="6135c-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="6135c-134">選擇`Run All`或運行此單個測試,並且它應該通過!</span><span class="sxs-lookup"><span data-stu-id="6135c-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6135c-135">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6135c-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6135c-136">要執行測試,請瀏覽到項目資料夾(包含`Tests.csproj`的資料夾),並執行以下指令:</span><span class="sxs-lookup"><span data-stu-id="6135c-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="6135c-137">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="6135c-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="6135c-138">儲存測試可以根據其名稱和/或執行目標進行篩選:</span><span class="sxs-lookup"><span data-stu-id="6135c-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="6135c-139">內部函數<xref:microsoft.quantum.intrinsic.message>具有`(String -> Unit)`類型 ,並能夠創建診斷消息。</span><span class="sxs-lookup"><span data-stu-id="6135c-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6135c-140">視覺工作室 2019</span><span class="sxs-lookup"><span data-stu-id="6135c-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6135c-141">在測試資源管理器中執行測試並按一下測試後,將顯示一個面板,其中將顯示有關測試執行的資訊:通過/失敗狀態、已用時間和"輸出"連結。</span><span class="sxs-lookup"><span data-stu-id="6135c-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="6135c-142">如果按下「輸出」連結,測試輸出將在新視窗中打開。</span><span class="sxs-lookup"><span data-stu-id="6135c-142">If you click the "Output" link, test output will open in a new window.</span></span>

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6135c-144">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6135c-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6135c-145">每個測試的通過/失敗狀態由`dotnet test`列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="6135c-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="6135c-146">對於失敗的測試,輸出也會列印到主控台,以幫助診斷故障。</span><span class="sxs-lookup"><span data-stu-id="6135c-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="6135c-147">事實與斷言</span><span class="sxs-lookup"><span data-stu-id="6135c-147">Facts and Assertions</span></span>

<span data-ttu-id="6135c-148">由於 Q# 中的函數沒有_邏輯_副作用,因此從 Q# 程式中永遠無法觀察到執行輸出`()`類型為空元組 的函數的任何其他_效果_。</span><span class="sxs-lookup"><span data-stu-id="6135c-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="6135c-149">也就是說,目標計算機可以選擇不執行返回的任何函數`()`,保證此遺漏不會修改以下任何 Q# 代碼的行為。</span><span class="sxs-lookup"><span data-stu-id="6135c-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="6135c-150">這使得函數返回`()`(`Unit`即 ) 成為將斷言和調試邏輯嵌入到 Q# 程式中的有用工具。</span><span class="sxs-lookup"><span data-stu-id="6135c-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="6135c-151">讓我們考慮一個簡單的範例:</span><span class="sxs-lookup"><span data-stu-id="6135c-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="6135c-152">此處,關鍵字`fail`指示計算不應繼續,從而在運行 Q# 程式的目標電腦中引發異常。</span><span class="sxs-lookup"><span data-stu-id="6135c-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="6135c-153">根據定義,無法從 Q# 內部觀察到此類故障,因為在到達語句後不會運行`fail`進一步的 Q# 代碼。</span><span class="sxs-lookup"><span data-stu-id="6135c-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="6135c-154">因此,如果我們通過調用`PositivityFact`,我們可以放心,它的意見是積極的。</span><span class="sxs-lookup"><span data-stu-id="6135c-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="6135c-155">請注意,我們可以實現與`PositivityFact`[`Fact`](xref:microsoft.quantum.diagnostics.fact)<xref:microsoft.quantum.diagnostics>使用 命名空間中的函數相同的行為:</span><span class="sxs-lookup"><span data-stu-id="6135c-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="6135c-156">另一方面,*斷言*與事實類似,但可能取決於目標計算機的狀態。</span><span class="sxs-lookup"><span data-stu-id="6135c-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="6135c-157">相應地,它們定義為操作,而事實定義為函數(如上所述)。</span><span class="sxs-lookup"><span data-stu-id="6135c-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="6135c-158">要理解區別,請考慮以下在斷言中使用事實:</span><span class="sxs-lookup"><span data-stu-id="6135c-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="6135c-159">在這裡,我們使用 該<xref:microsoft.quantum.environment.getqubitsavailabletouse>操作返回可供使用的量子位數。</span><span class="sxs-lookup"><span data-stu-id="6135c-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="6135c-160">由於這顯然取決於程式的全域狀態及其執行環境,因此我們的定義`AssertQubitsAreAvailable`也必須是操作。</span><span class="sxs-lookup"><span data-stu-id="6135c-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="6135c-161">但是,我們可以使用該全域狀態生成一個簡單的`Bool`值作為函數的`Fact`輸入。</span><span class="sxs-lookup"><span data-stu-id="6135c-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="6135c-162">在這些想法的基礎上[,前奏](xref:microsoft.quantum.libraries.standard.prelude)提供了兩個特別有用的斷<xref:microsoft.quantum.intrinsic.assert>言<xref:microsoft.quantum.intrinsic.assertprob>, 兩`()`者都模仿到 上的操作。</span><span class="sxs-lookup"><span data-stu-id="6135c-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="6135c-163">這些斷言每個都採用一個 Pauli 運算符來描述特定的興趣測量、要對其進行測量的量子寄存器以及假設結果。</span><span class="sxs-lookup"><span data-stu-id="6135c-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="6135c-164">在通過類比工作的目標機器上,我們不受[無克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的約束,可以執行這種測量,而不會干擾傳遞給此類斷言的寄存器。</span><span class="sxs-lookup"><span data-stu-id="6135c-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="6135c-165">然後,如果在實踐中無法觀察到假設結果`PositivityFact`,模擬器可以中止計算,類似於上面的函數:</span><span class="sxs-lookup"><span data-stu-id="6135c-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="6135c-166">在物理量子硬體上,無克隆定理阻止量子狀態的檢查,`Assert``AssertProb`和 操作`()`只是返回 ,沒有其他效果。</span><span class="sxs-lookup"><span data-stu-id="6135c-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="6135c-167">命名<xref:microsoft.quantum.diagnostics>空間`Assert`提供了多個系列的函數,使我們能夠檢查更高級的條件。</span><span class="sxs-lookup"><span data-stu-id="6135c-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="6135c-168">傾印函數</span><span class="sxs-lookup"><span data-stu-id="6135c-168">Dump Functions</span></span>

<span data-ttu-id="6135c-169">為了協助對量子程式進行故障排除,<xref:microsoft.quantum.diagnostics>命名空間提供了兩個函數,可以轉儲到檔案中的目標電腦的當前狀態<xref:microsoft.quantum.diagnostics.dumpmachine>:<xref:microsoft.quantum.diagnostics.dumpregister>和 。</span><span class="sxs-lookup"><span data-stu-id="6135c-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="6135c-170">每個機器的生成輸出取決於目標計算機。</span><span class="sxs-lookup"><span data-stu-id="6135c-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="6135c-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="6135c-171">DumpMachine</span></span>

<span data-ttu-id="6135c-172">作為量子開發工具組的一部分分佈的全態量子模擬器將整個量子系統的[波函數](https://en.wikipedia.org/wiki/Wave_function)寫入檔,作為一維的複數陣列,其中每個元素表示測量計算基礎狀態 $_ket_n$的概率的振幅,其中 $ket\n} = \ket\n= [ket\b_{n]...b_1b_0_$為位\{$b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="6135c-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="6135c-173">例如,在只分配兩個量子位且處於量子狀態的計算機上,$$_開始\對齊_ket_psi}{1}= _frac{2}[sqrt]{00} \ket - [frac](1 ={2} i)]\ket,[end]###$${10}調用<xref:microsoft.quantum.diagnostics.dumpmachine>將生成此輸出:</span><span class="sxs-lookup"><span data-stu-id="6135c-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="6135c-174">第一行按重要順序提供具有相應量子位的的的註釋。</span><span class="sxs-lookup"><span data-stu-id="6135c-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="6135c-175">其餘行描述以笛卡爾和極性格式測量基礎狀態向量 $_ket_n_$ 的概率振幅。</span><span class="sxs-lookup"><span data-stu-id="6135c-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="6135c-176">詳細介紹第一行:</span><span class="sxs-lookup"><span data-stu-id="6135c-176">In detail for the first row:</span></span>

* <span data-ttu-id="6135c-177">**`∣0❭:`** 此行對應於`0`計算基礎狀態</span><span class="sxs-lookup"><span data-stu-id="6135c-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="6135c-178">**`0.707107 +  0.000000 i`**:以笛卡爾格式表示的概率振幅。</span><span class="sxs-lookup"><span data-stu-id="6135c-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="6135c-179">**` == `**:符號`equal`分離兩個等效表示形式。</span><span class="sxs-lookup"><span data-stu-id="6135c-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="6135c-180">**`**********  `**: 震級的圖形表示,`*`數量 與測量此狀態向量的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="6135c-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="6135c-181">**`[ 0.500000 ]`**:震級的數值</span><span class="sxs-lookup"><span data-stu-id="6135c-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="6135c-182">**`    ---`**: 振幅相的圖形表示(見下文)。</span><span class="sxs-lookup"><span data-stu-id="6135c-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="6135c-183">**`[ 0.0000 rad ]`**:相位的數值(以弧度表示)。</span><span class="sxs-lookup"><span data-stu-id="6135c-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="6135c-184">大小和相位都顯示圖形表示。</span><span class="sxs-lookup"><span data-stu-id="6135c-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="6135c-185">幅度表示是直截了當的:它顯示一個柱線`*`,柱值的概率越大。</span><span class="sxs-lookup"><span data-stu-id="6135c-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="6135c-186">對於相位,我們顯示以下符號以表示基於範圍的角度:</span><span class="sxs-lookup"><span data-stu-id="6135c-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="6135c-187">以下範例顯示了`DumpMachine`某些常見狀態:</span><span class="sxs-lookup"><span data-stu-id="6135c-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="6135c-188">qubit 的 ID 在執行時分配,它不一定與分配 qubit 的順序或其在 qubit 寄存器中的位置保持一致。</span><span class="sxs-lookup"><span data-stu-id="6135c-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6135c-189">視覺工作室 2019</span><span class="sxs-lookup"><span data-stu-id="6135c-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="6135c-190">您可以透過在代碼中放置中斷點並檢查 qubit 變數的值來在 Visual Studio 中找出 qubit ID,例如:</span><span class="sxs-lookup"><span data-stu-id="6135c-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在視覺工作室中顯示 qubit ID](~/media/qubit_id.png)
  >
  > <span data-ttu-id="6135c-192">`0`索引上的`register2`qubit 的代碼`3`= , 索`1`引`2`的 qubit 具有 id= 。</span><span class="sxs-lookup"><span data-stu-id="6135c-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6135c-193">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6135c-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="6135c-194">您可以透過<xref:microsoft.quantum.intrinsic.message>使用函數並傳遞訊息中的 qubit 變數來找出 qubit ID,例如:</span><span class="sxs-lookup"><span data-stu-id="6135c-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="6135c-195">可以產生此輸出:</span><span class="sxs-lookup"><span data-stu-id="6135c-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="6135c-196">這`0``register2`表示 索引上的 qubit`3`具有 id_,`1`索引`2`的 qubit 具有 id= 。</span><span class="sxs-lookup"><span data-stu-id="6135c-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="6135c-197"><xref:microsoft.quantum.diagnostics.dumpmachine>是命名空間的<xref:microsoft.quantum.diagnostics>一部分,因此為了使用它,您必須添加一個`open`語句:</span><span class="sxs-lookup"><span data-stu-id="6135c-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="6135c-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="6135c-198">DumpRegister</span></span>

<span data-ttu-id="6135c-199"><xref:microsoft.quantum.diagnostics.dumpregister>工作方式<xref:microsoft.quantum.diagnostics.dumpmachine>如下,只不過還需要一個量子位數組來將資訊量限制為僅與相應量子位相關的資訊量。</span><span class="sxs-lookup"><span data-stu-id="6135c-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="6135c-200">與<xref:microsoft.quantum.diagnostics.dumpmachine>,<xref:microsoft.quantum.diagnostics.dumpregister>生成 的資訊取決於目標計算機。</span><span class="sxs-lookup"><span data-stu-id="6135c-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="6135c-201">對於全態量子模擬器,它將波函數寫入到量子子系統的全域階段<xref:microsoft.quantum.diagnostics.dumpmachine>,該子系統由提供的量子位以與的格式相同。</span><span class="sxs-lookup"><span data-stu-id="6135c-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="6135c-202">例如, 再次拍攝一台只分配兩個量子位且處於量子狀態的機器 $$開始 \ket_psi} ={1}_frac _sqrt{2}{00} = ket - [frac[1{2} = i]\ket{0} {2} {1} {2}{0}<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[0]`{10} = - e_-i_pi/4{1}\* ({2}[frac ]sqrt = \ket - [frac](1 = i)] \ket) \fc_-(1 = i)][sqrt] \ket),[ 結束]\align= $$$$$s 調用 生成 此輸出:</span><span class="sxs-lookup"><span data-stu-id="6135c-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="6135c-203">並呼叫<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`產生此輸出:</span><span class="sxs-lookup"><span data-stu-id="6135c-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="6135c-204">通常,與另一個寄存器糾纏的寄存器狀態是混合狀態,而不是純狀態。</span><span class="sxs-lookup"><span data-stu-id="6135c-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="6135c-205">在這種情況下,<xref:microsoft.quantum.diagnostics.dumpregister>輸出以下訊息:</span><span class="sxs-lookup"><span data-stu-id="6135c-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="6135c-206">下面的範例展示如何在 Q# 代碼<xref:microsoft.quantum.diagnostics.dumpregister>中<xref:microsoft.quantum.diagnostics.dumpmachine>使用兩 者:</span><span class="sxs-lookup"><span data-stu-id="6135c-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="6135c-207">偵錯</span><span class="sxs-lookup"><span data-stu-id="6135c-207">Debugging</span></span>

<span data-ttu-id="6135c-208">除了函數與`Assert``Dump`操作,Q# 還支援標準 Visual Studio 除錯功能的子集:在模擬器上的程式碼執行期間,可以使用 F10[設定線斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints),[單步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)以及[檢查經典變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)。</span><span class="sxs-lookup"><span data-stu-id="6135c-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="6135c-209">從 Visual Studio 程式碼中的除錯利用由 OmniSharp 提供支援的 Visual Studio 程式碼延伸 C# 提供的除錯功能,並且需要安裝[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="6135c-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
