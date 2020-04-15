---
title: 量子模擬器和主應用程式 | Microsoft Docs
description: 說明如何使用傳統運算的 .NET 語言 (通常是 C# 或 Q#) 來驅動量子模擬器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442221"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="55449-103">量子模擬器和主應用程式</span><span class="sxs-lookup"><span data-stu-id="55449-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="55449-104">您會學習到的知識</span><span class="sxs-lookup"><span data-stu-id="55449-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="55449-105">執行量子演算法的方法</span><span class="sxs-lookup"><span data-stu-id="55449-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="55449-106">此版本包含哪些量子模擬器</span><span class="sxs-lookup"><span data-stu-id="55449-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="55449-107">如何為量子演算法編寫 C# 驅動程式</span><span class="sxs-lookup"><span data-stu-id="55449-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="55449-108">Quantum Development Kit 執行模型</span><span class="sxs-lookup"><span data-stu-id="55449-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="55449-109">在[編寫量子程式](xref:microsoft.quantum.write-program)中，我們藉由將 `QuantumSimulator` 物件傳遞給演算法類別的 `Run` 方法，執行了我們的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="55449-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="55449-110">`QuantumSimulator` 類別會藉由完全模擬量子態向量來執行量子演算法，這種做法非常適合用來執行和測試 `Teleport`。</span><span class="sxs-lookup"><span data-stu-id="55449-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="55449-111">如需量子態向量的詳細資訊，請參閱[概念指南](xref:microsoft.quantum.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="55449-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="55449-112">其他目標機器也可用來執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="55449-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="55449-113">該機器會負責為演算法提供量子基元實作。</span><span class="sxs-lookup"><span data-stu-id="55449-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="55449-114">這包括基元操作，例如 H、CNOT 和 Measure，以及量子位元管理和追蹤。</span><span class="sxs-lookup"><span data-stu-id="55449-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="55449-115">不同類別的量子機器代表相同量子演算法的不同執行模型。</span><span class="sxs-lookup"><span data-stu-id="55449-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="55449-116">每種量子機器都可以針對這些基元提供不同的實作。</span><span class="sxs-lookup"><span data-stu-id="55449-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="55449-117">例如，Development Kit 中包含的量子電腦追蹤模擬器就完全不會進行任何模擬。</span><span class="sxs-lookup"><span data-stu-id="55449-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="55449-118">相反地，該模擬器會追蹤該演算法的量子閘、量子位元和其他資源使用狀況。</span><span class="sxs-lookup"><span data-stu-id="55449-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="55449-119">量子機器</span><span class="sxs-lookup"><span data-stu-id="55449-119">Quantum Machines</span></span>

<span data-ttu-id="55449-120">在未來，我們將定義其他量子機器類別，以支援其他類型的模擬，以及支援拓撲量子電腦上的執行作業。</span><span class="sxs-lookup"><span data-stu-id="55449-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="55449-121">讓演算法可以在改變基礎機器實作的情況下保持不變，您就可以輕鬆地在模擬中測試演算法並進行偵錯，然後再於真正的硬體上執行，因為您知道演算法並未改變。</span><span class="sxs-lookup"><span data-stu-id="55449-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="55449-122">此版本包含的類別</span><span class="sxs-lookup"><span data-stu-id="55449-122">What's Included in this Release</span></span>

<span data-ttu-id="55449-123">這一版的 Quantum Developer Kit 包含數個量子機器類別。</span><span class="sxs-lookup"><span data-stu-id="55449-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="55449-124">這些類別全都定義在 `Microsoft.Quantum.Simulation.Simulators` 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="55449-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="55449-125">[完整狀態向量模擬器](xref:microsoft.quantum.machines.full-state-simulator)，`QuantumSimulator` 類別。</span><span class="sxs-lookup"><span data-stu-id="55449-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="55449-126">[簡單的資源估算器](xref:microsoft.quantum.machines.resources-estimator)，`ResourcesEstimator` 類別，其可讓您對執行量子演算法所需的資源進行最上層的分析。</span><span class="sxs-lookup"><span data-stu-id="55449-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="55449-127">[追蹤型資源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)，`QCTraceSimulator` 類別，其可讓您針對演算法整個呼叫圖的資源耗用情形進行進階分析。</span><span class="sxs-lookup"><span data-stu-id="55449-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="55449-128">[Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)，`ToffoliSimulator` 類別。</span><span class="sxs-lookup"><span data-stu-id="55449-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="55449-129">撰寫主應用程式</span><span class="sxs-lookup"><span data-stu-id="55449-129">Writing a host application</span></span>

<span data-ttu-id="55449-130">在[撰寫量子程式](xref:microsoft.quantum.write-program)中，我們針對遙傳演算法編寫了簡單的 C# 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="55449-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="55449-131">C# 驅動程式有 4 個主要目的：</span><span class="sxs-lookup"><span data-stu-id="55449-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="55449-132">建構目標機器</span><span class="sxs-lookup"><span data-stu-id="55449-132">Constructing the target machine</span></span>
* <span data-ttu-id="55449-133">計算量子演算法所需的任何引數</span><span class="sxs-lookup"><span data-stu-id="55449-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="55449-134">使用模擬器執行量子演算法</span><span class="sxs-lookup"><span data-stu-id="55449-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="55449-135">處理操作結果</span><span class="sxs-lookup"><span data-stu-id="55449-135">Processing the result of the operation</span></span>

<span data-ttu-id="55449-136">在這裡，我們會更詳細地討論每個步驟。</span><span class="sxs-lookup"><span data-stu-id="55449-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="55449-137">建構目標機器</span><span class="sxs-lookup"><span data-stu-id="55449-137">Constructing the Target Machine</span></span>

<span data-ttu-id="55449-138">量子機器是一般 .NET 類別的執行個體，因此可藉由叫用其建構函式來加以建立，就和任何 .NET 類別一樣。</span><span class="sxs-lookup"><span data-stu-id="55449-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="55449-139">某些模擬器 (包括 `QuantumSimulator`) 會實作 .NET <xref:System.IDisposable?displayProperty=nameWithType> 介面，因此應該包裝到 C# `using` 陳述式中。</span><span class="sxs-lookup"><span data-stu-id="55449-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="55449-140">計算演算法的引數</span><span class="sxs-lookup"><span data-stu-id="55449-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="55449-141">在 `Teleport` 範例中，我們計算了一些相當不自然的引數，來傳遞至我們的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="55449-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="55449-142">不過，更常見的情況是，量子演算法需要大量資料，而從傳統驅動程式提供這些資料會最為簡單。</span><span class="sxs-lookup"><span data-stu-id="55449-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="55449-143">例如，在進行化學模擬時，量子演算法需要分子軌道相互作用積分法所形成的大型資料表。</span><span class="sxs-lookup"><span data-stu-id="55449-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="55449-144">一般而言，這些積分法會從執行演算法時所提供的檔案中讀取而來。</span><span class="sxs-lookup"><span data-stu-id="55449-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="55449-145">由於 Q# 沒有存取檔案系統的機制，因此這類資料最好由傳統驅動程式收集，再傳遞給量子演算法的 `Run` 方法。</span><span class="sxs-lookup"><span data-stu-id="55449-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="55449-146">傳統驅動程式會扮演重要角色的另一種情況是在變分方法中。</span><span class="sxs-lookup"><span data-stu-id="55449-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="55449-147">這個演算法類別會根據一些傳統參數來準備量子態，並用該量子態來計算一些感興趣的值。</span><span class="sxs-lookup"><span data-stu-id="55449-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="55449-148">這些參數會根據某種類型的爬山演算法或機器學習演算法進行調整，然後再重新執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="55449-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="55449-149">對於這類演算法，爬山演算法本身最好實作為純粹的傳統函式以供傳統驅動程式呼叫；然後，再將爬山演算法的結果傳遞給量子演算法的下一次執行。</span><span class="sxs-lookup"><span data-stu-id="55449-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="55449-150">執行量子演算法</span><span class="sxs-lookup"><span data-stu-id="55449-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="55449-151">這個部分通常非常簡單。</span><span class="sxs-lookup"><span data-stu-id="55449-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="55449-152">每個 Q# 操作都會編譯成可提供靜態 `Run` 方法的類別。</span><span class="sxs-lookup"><span data-stu-id="55449-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="55449-153">這個方法的引數是由操作本身的簡維引數元組所提供，再加上另外要在執行模擬器時搭配使用的第一個引數。</span><span class="sxs-lookup"><span data-stu-id="55449-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="55449-154">對於預期具名元組的類型為 `(a: String, (b: Double, c: Double))` 的操作，其簡維對應項的類型為 `(String a, Double b, Double c)`。</span><span class="sxs-lookup"><span data-stu-id="55449-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="55449-155">在將引數傳遞給 `Run` 方法時，會有一些微妙差異：</span><span class="sxs-lookup"><span data-stu-id="55449-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="55449-156">陣列必須包裝在 `Microsoft.Quantum.Simulation.Core.QArray<T>` 物件中。</span><span class="sxs-lookup"><span data-stu-id="55449-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="55449-157">`QArray` 類別所具有的建構函式可接受適當物件的任何已排序集合 (`IEnumerable<T>`)。</span><span class="sxs-lookup"><span data-stu-id="55449-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="55449-158">Q# 中的空白元組 `()` 在 C# 中會以 `QVoid.Instance` 表示。</span><span class="sxs-lookup"><span data-stu-id="55449-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="55449-159">非空白元組則會表示為 .NET `ValueTuple` 執行個體。</span><span class="sxs-lookup"><span data-stu-id="55449-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="55449-160">Q# 的使用者定義型別會以其基底類型的形式來傳遞。</span><span class="sxs-lookup"><span data-stu-id="55449-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="55449-161">若要將操作或函式傳遞給 `Run` 方法，您必須使用模擬器的 `Get<>` 方法，取得操作或函式類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="55449-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="55449-162">處理結果</span><span class="sxs-lookup"><span data-stu-id="55449-162">Processing the Results</span></span>

<span data-ttu-id="55449-163">量子演算法的結果會從 `Run` 方法傳回。</span><span class="sxs-lookup"><span data-stu-id="55449-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="55449-164">`Run` 方法會以非同步方式執行，因此會傳回 <xref:System.Threading.Tasks.Task`1> 的執行個體。</span><span class="sxs-lookup"><span data-stu-id="55449-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="55449-165">有多種方式可取得實際操作的結果。</span><span class="sxs-lookup"><span data-stu-id="55449-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="55449-166">最簡單的方式是使用 `Task` 的 [`Result` 屬性](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)：</span><span class="sxs-lookup"><span data-stu-id="55449-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="55449-167">但使用其他技術 (如使用 [`Wait` 方法](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) 或 C# [`await` 關鍵字](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)) 也行。</span><span class="sxs-lookup"><span data-stu-id="55449-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="55449-168">如同引數，Q# 元組會表示為 `ValueTuple` 執行個體，而 Q# 陣列則會表示為 `QArray` 執行個體。</span><span class="sxs-lookup"><span data-stu-id="55449-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="55449-169">使用者定義型別會以其基底類型的形式來傳回。</span><span class="sxs-lookup"><span data-stu-id="55449-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="55449-170">空白元組 `()` 會以 `QVoid` 類別的執行個體形式來傳回。</span><span class="sxs-lookup"><span data-stu-id="55449-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="55449-171">許多量子演算法都需要大量後期處理才能衍生出有用的答案。</span><span class="sxs-lookup"><span data-stu-id="55449-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="55449-172">例如，Shor 演算法的量子部分只是計算的開端，目的是要尋找某個數字的因數。</span><span class="sxs-lookup"><span data-stu-id="55449-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="55449-173">大部分情況下，在傳統驅動程式中執行這類後期處理最為簡單容易。</span><span class="sxs-lookup"><span data-stu-id="55449-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="55449-174">只有傳統驅動程式可以向使用者報告結果，或將結果寫入到磁碟。</span><span class="sxs-lookup"><span data-stu-id="55449-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="55449-175">傳統驅動程式將可存取分析程式庫，以及未在 Q# 中公開的其他數學函式。</span><span class="sxs-lookup"><span data-stu-id="55449-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="55449-176">失敗</span><span class="sxs-lookup"><span data-stu-id="55449-176">Failures</span></span>

<span data-ttu-id="55449-177">在執行操作期間到達 Q# `fail` 陳述式時，系統會擲回 `ExecutionFailException`。</span><span class="sxs-lookup"><span data-stu-id="55449-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="55449-178">由於在 `Run` 方法中使用 `System.Task`，因此在到達 `fail` 陳述式時所擲回的例外狀況將會包裝到 `System.AggregateException` 中。</span><span class="sxs-lookup"><span data-stu-id="55449-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="55449-179">若要找出失敗的實際原因，您必須反覆執行到 `AggregateException` 
`InnerExceptions`，例如：</span><span class="sxs-lookup"><span data-stu-id="55449-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="55449-180">其他傳統語言</span><span class="sxs-lookup"><span data-stu-id="55449-180">Other Classical Languages</span></span>

<span data-ttu-id="55449-181">雖然我們提供的範例採用的是 C#、F# 和 Python，但 Quantum Development Kit 也支援使用其他語言來編寫傳統的主機程式。</span><span class="sxs-lookup"><span data-stu-id="55449-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="55449-182">例如，如果您想要採用 Visual Basic 來編寫主機程式，[應該也不會有問題](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。</span><span class="sxs-lookup"><span data-stu-id="55449-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
