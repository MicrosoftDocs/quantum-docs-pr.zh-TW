---
title: 量子資源估算器-量子開發工具組
description: 深入瞭解 Microsoft QDK resources 估算器，其預估在量子電腦上執行特定作業實例所需的資源 Q# 。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604638"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="4b522-103">量子開發工具組 (QDK) 資源估算器</span><span class="sxs-lookup"><span data-stu-id="4b522-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="4b522-104">顧名思義，類別會估計在 `ResourcesEstimator` 量子電腦上執行某項作業的指定實例所需的資源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="4b522-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="4b522-105">它是藉由執行量子操作來完成，而不實際模擬量子電腦的狀態;基於這個原因，它會針對 Q# 使用上千個量子位的作業預估資源，前提是程式碼的傳統部分在合理的時間內執行。</span><span class="sxs-lookup"><span data-stu-id="4b522-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="4b522-106">資源估算器建置於 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器之上，它提供了一組更豐富的計量和工具來協助您進行調試 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="4b522-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="4b522-107">叫用和執行資源估算器</span><span class="sxs-lookup"><span data-stu-id="4b522-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="4b522-108">您可以使用 [資源] 估算器來執行任何作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="4b522-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="4b522-109">如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="4b522-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="4b522-110">叫用從 C 估算器的資源#</span><span class="sxs-lookup"><span data-stu-id="4b522-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="4b522-111">就像其他目標機器一樣，您必須先建立 `ResourcesEstimator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。</span><span class="sxs-lookup"><span data-stu-id="4b522-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="4b522-112">請注意，不同於 `QuantumSimulator` 類別，`ResourcesEstimator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。</span><span class="sxs-lookup"><span data-stu-id="4b522-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="4b522-113">如範例所示，會 `ResourcesEstimator` 提供 `ToTSV()` 方法，此方法會產生一個具有定位字元分隔值的資料表 (TSV) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="4b522-114">您可以將資料表儲存至檔案，或將它顯示在主控台進行分析。</span><span class="sxs-lookup"><span data-stu-id="4b522-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="4b522-115">以下是先前程式的輸出範例：</span><span class="sxs-lookup"><span data-stu-id="4b522-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="4b522-116">`ResourcesEstimator`實例不會在每次執行時重設其計算。</span><span class="sxs-lookup"><span data-stu-id="4b522-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="4b522-117">如果您使用相同的實例來執行另一個作業，它會使用現有的結果來匯總新的結果。</span><span class="sxs-lookup"><span data-stu-id="4b522-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="4b522-118">如果您需要重設執行之間的計算，請針對每次執行建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="4b522-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="4b522-119">從 Python 叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="4b522-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="4b522-120">使用匯入作業，從 Python 程式庫使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="4b522-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="4b522-121">從命令列叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="4b522-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="4b522-122">Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s** 快速鍵) 參數來指定 `ResourcesEstimator` 目的電腦。</span><span class="sxs-lookup"><span data-stu-id="4b522-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="4b522-123">下列命令會使用資源估算器來執行程式：</span><span class="sxs-lookup"><span data-stu-id="4b522-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="4b522-124">從 Juptyer 筆記本叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="4b522-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="4b522-125">使用 I Q# 魔術命令 [% 估計](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 來執行此作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="4b522-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="4b522-126">以程式設計方式取出預估資料</span><span class="sxs-lookup"><span data-stu-id="4b522-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="4b522-127">除了 TSV 資料表以外，您也可以透過程式設計方式，透過 [資源] 估算器的屬性，在執行期間取得估計的資源 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="4b522-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="4b522-128">`Data`屬性提供 `System.DataTable` 具有兩個數據行的實例： `Metric` 和 `Sum` ，由度量的名稱索引。</span><span class="sxs-lookup"><span data-stu-id="4b522-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="4b522-129">下列程式碼示範如何取出和列印工作所使用的總 `QubitClifford` 次數 `T` 和 `CNOT` 作業 Q# ：</span><span class="sxs-lookup"><span data-stu-id="4b522-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="4b522-130">回報的計量</span><span class="sxs-lookup"><span data-stu-id="4b522-130">Metrics Reported</span></span>

<span data-ttu-id="4b522-131">資源估算器會追蹤下列計量：</span><span class="sxs-lookup"><span data-stu-id="4b522-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="4b522-132">計量</span><span class="sxs-lookup"><span data-stu-id="4b522-132">Metric</span></span>|<span data-ttu-id="4b522-133">描述</span><span class="sxs-lookup"><span data-stu-id="4b522-133">Description</span></span>|
|----|----|
|<span data-ttu-id="4b522-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="4b522-134">__CNOT__</span></span>    |<span data-ttu-id="4b522-135">作業的執行計數 `CNOT` (也稱為受控 Pauli X 作業) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="4b522-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="4b522-136">__QubitClifford__</span></span> |<span data-ttu-id="4b522-137">任何單一量子位 Clifford 和 Pauli 作業的執行計數。</span><span class="sxs-lookup"><span data-stu-id="4b522-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="4b522-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="4b522-138">__Measure__</span></span>    |<span data-ttu-id="4b522-139">任何測量的執行計數。</span><span class="sxs-lookup"><span data-stu-id="4b522-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="4b522-140">__R__</span><span class="sxs-lookup"><span data-stu-id="4b522-140">__R__</span></span>    |<span data-ttu-id="4b522-141">任何單一量子位旋轉、排除 `T` 、Clifford 和 Pauli 作業的執行計數。</span><span class="sxs-lookup"><span data-stu-id="4b522-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="4b522-142">__T__</span><span class="sxs-lookup"><span data-stu-id="4b522-142">__T__</span></span>    |<span data-ttu-id="4b522-143">作業的執行計數 `T` 和其 conjugates，包括 `T` 作業、T_x = .h 和 T_y = Hy Hy。</span><span class="sxs-lookup"><span data-stu-id="4b522-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="4b522-144">__深度__</span><span class="sxs-lookup"><span data-stu-id="4b522-144">__Depth__</span></span>|<span data-ttu-id="4b522-145">作業所執行的量子線路深度 Q# (請參閱 [以下](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="4b522-146">根據預設，深度度量只會計算網 `T` 關。</span><span class="sxs-lookup"><span data-stu-id="4b522-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="4b522-147">如需詳細資訊，請參閱 [深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="4b522-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="4b522-148">__寬度__</span><span class="sxs-lookup"><span data-stu-id="4b522-148">__Width__</span></span>|<span data-ttu-id="4b522-149">作業所執行的量子電路寬度 Q# (請參閱 [以下](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="4b522-150">根據預設，深度度量只會計算網 `T` 關。</span><span class="sxs-lookup"><span data-stu-id="4b522-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="4b522-151">如需詳細資訊，請參閱 [Width 計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。</span><span class="sxs-lookup"><span data-stu-id="4b522-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="4b522-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="4b522-152">__QubitCount__</span></span>    |<span data-ttu-id="4b522-153">作業執行期間所配置的最大量子位數目下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="4b522-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="4b522-154">此計量可能與 __深度__ (不相容，請參閱下面的) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="4b522-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="4b522-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="4b522-156">在作業內借用的量子位數目上限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="4b522-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="4b522-157">深度、寬度和 QubitCount</span><span class="sxs-lookup"><span data-stu-id="4b522-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="4b522-158">報告的深度和寬度估計值彼此相容。</span><span class="sxs-lookup"><span data-stu-id="4b522-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="4b522-159"> (先前兩個數字都是可達成的，但深度和寬度都需要不同的電路。 ) 這組中的計量目前可由相同的線路同時達成。</span><span class="sxs-lookup"><span data-stu-id="4b522-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="4b522-160">系統會報告下列計量：</span><span class="sxs-lookup"><span data-stu-id="4b522-160">The following metrics are reported:</span></span>

<span data-ttu-id="4b522-161">__深度：__ 針對根作業，它會假設特定的閘道時間來執行它。</span><span class="sxs-lookup"><span data-stu-id="4b522-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="4b522-162">針對呼叫的作業或後續的作業-在最新的量子位可用性時間與作業結束之間的時間差異。</span><span class="sxs-lookup"><span data-stu-id="4b522-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="4b522-163">__寬度：__ 針對根本操作（量子位實際用來執行它的數目） (和作業，它會呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="4b522-164">針對呼叫的作業或後續作業-已使用的量子位數目，以及在作業開始時使用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="4b522-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="4b522-165">請注意，重複使用的量子位並不會影響到這個數位。</span><span class="sxs-lookup"><span data-stu-id="4b522-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="4b522-166">亦即，如果在作業 A 開始之前已釋出幾個量子位，而且此作業要求的所有量子位都是藉由重複使用先前的發行量子位來滿足) 的 (和作業，則作業 A 的寬度會回報為0。</span><span class="sxs-lookup"><span data-stu-id="4b522-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="4b522-167">成功的借用量子位不會影響到寬度。</span><span class="sxs-lookup"><span data-stu-id="4b522-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="4b522-168">__QubitCount：__ 若為根作業，則為執行此作業所需的最小量子位數目 (以及從中呼叫的作業) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="4b522-169">針對呼叫的作業或後續的作業，也就是足以個別執行此作業的量子位數目下限。</span><span class="sxs-lookup"><span data-stu-id="4b522-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="4b522-170">此數目不包含輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="4b522-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="4b522-171">它包含借用量子位。</span><span class="sxs-lookup"><span data-stu-id="4b522-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="4b522-172">支援兩種作業模式。</span><span class="sxs-lookup"><span data-stu-id="4b522-172">Two modes of operation are supported.</span></span> <span data-ttu-id="4b522-173">您可以藉由設定 QCTraceSimulatorConfiguration OptimizeDepth 來選取模式。</span><span class="sxs-lookup"><span data-stu-id="4b522-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="4b522-174">__OptimizeDepth = true：__ QubitManager 不建議量子位重複使用，並且會在每次要求量子位時配置新的量子位。</span><span class="sxs-lookup"><span data-stu-id="4b522-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="4b522-175">針對根操作 __深度__ ，會變成 (下限) 的最小深度。</span><span class="sxs-lookup"><span data-stu-id="4b522-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="4b522-176">此深度會回報相容的 __寬度__ ， (可以同時) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="4b522-177">請注意，此寬度在此深度中可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="4b522-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="4b522-178">__QubitCount__ 可能會比根作業的寬度低，因為它會假設重複使用。</span><span class="sxs-lookup"><span data-stu-id="4b522-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="4b522-179">__OptimizeDepth = false：__ 建議 QubitManager 使用量子位，並在配置新的量子位之前重複使用已發行的。</span><span class="sxs-lookup"><span data-stu-id="4b522-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="4b522-180">針對根作業 __寬度__ ，會變成最小寬度 (下限) 。</span><span class="sxs-lookup"><span data-stu-id="4b522-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="4b522-181">您可以在其上取得相容 __深度__ 的報告。</span><span class="sxs-lookup"><span data-stu-id="4b522-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="4b522-182">__QubitCount__ 將與根本作業的 __寬度__ 相同（假設沒有借用）。</span><span class="sxs-lookup"><span data-stu-id="4b522-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="4b522-183">提供測量結果的機率</span><span class="sxs-lookup"><span data-stu-id="4b522-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="4b522-184">您可以 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 從 <xref:Microsoft.Quantum.Diagnostics> 命名空間使用，以提供有關測量運算之預期機率的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b522-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="4b522-185">如需詳細資訊，請參閱[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器</span><span class="sxs-lookup"><span data-stu-id="4b522-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="4b522-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4b522-186">See also</span></span>

- [<span data-ttu-id="4b522-187">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="4b522-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="4b522-188">量子 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="4b522-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="4b522-189">量子完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="4b522-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
