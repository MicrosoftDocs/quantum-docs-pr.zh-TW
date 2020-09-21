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
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835922"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="42ae1-103">量子開發工具組 (QDK) 資源估算器</span><span class="sxs-lookup"><span data-stu-id="42ae1-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="42ae1-104">顧名思義，類別會估計在 `ResourcesEstimator` 量子電腦上執行某項作業的指定實例所需的資源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="42ae1-105">它是藉由執行量子操作來完成，而不實際模擬量子電腦的狀態;基於這個原因，它會針對 Q# 使用上千個量子位的作業預估資源，前提是程式碼的傳統部分在合理的時間內執行。</span><span class="sxs-lookup"><span data-stu-id="42ae1-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="42ae1-106">資源估算器建置於 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器之上，它提供了一組更豐富的計量和工具來協助您進行調試 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="42ae1-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="42ae1-107">叫用和執行資源估算器</span><span class="sxs-lookup"><span data-stu-id="42ae1-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="42ae1-108">您可以使用 [資源] 估算器來執行任何作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="42ae1-109">如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="42ae1-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="42ae1-110">叫用從 C 估算器的資源#</span><span class="sxs-lookup"><span data-stu-id="42ae1-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="42ae1-111">就像其他目標機器一樣，您必須先建立 `ResourceEstimator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。</span><span class="sxs-lookup"><span data-stu-id="42ae1-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="42ae1-112">請注意，不同於 `QuantumSimulator` 類別，`ResourceEstimator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。</span><span class="sxs-lookup"><span data-stu-id="42ae1-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="42ae1-113">如範例所示，會 `ResourcesEstimator` 提供 `ToTSV()` 方法，此方法會產生一個具有定位字元分隔值的資料表 (TSV) 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="42ae1-114">您可以將資料表儲存至檔案，或將它顯示在主控台進行分析。</span><span class="sxs-lookup"><span data-stu-id="42ae1-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="42ae1-115">以下是先前程式的輸出範例：</span><span class="sxs-lookup"><span data-stu-id="42ae1-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="42ae1-116">`ResourcesEstimator`實例不會在每次執行時重設其計算。</span><span class="sxs-lookup"><span data-stu-id="42ae1-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="42ae1-117">如果您使用相同的實例來執行另一個作業，它會使用現有的結果來匯總新的結果。</span><span class="sxs-lookup"><span data-stu-id="42ae1-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="42ae1-118">如果您需要重設執行之間的計算，請針對每次執行建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="42ae1-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="42ae1-119">從 Python 叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="42ae1-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="42ae1-120">使用匯入作業，從 Python 程式庫使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="42ae1-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="42ae1-121">從命令列叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="42ae1-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="42ae1-122">Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s**快速鍵) 參數來指定 `ResourcesEstimator` 目的電腦。</span><span class="sxs-lookup"><span data-stu-id="42ae1-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="42ae1-123">下列命令會使用資源估算器來執行程式：</span><span class="sxs-lookup"><span data-stu-id="42ae1-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="42ae1-124">從 Juptyer 筆記本叫用資源估算器</span><span class="sxs-lookup"><span data-stu-id="42ae1-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="42ae1-125">使用 I Q# 魔術命令 [% 估計](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 來執行此作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="42ae1-126">以程式設計方式取出預估資料</span><span class="sxs-lookup"><span data-stu-id="42ae1-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="42ae1-127">除了 TSV 資料表以外，您也可以透過程式設計方式，透過 [資源] 估算器的屬性，在執行期間取得估計的資源 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="42ae1-128">`Data`屬性提供 `System.DataTable` 具有兩個數據行的實例： `Metric` 和 `Sum` ，由度量的名稱索引。</span><span class="sxs-lookup"><span data-stu-id="42ae1-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="42ae1-129">下列程式碼示範如何取出和列印工作所使用的總 `QubitClifford` 次數 `T` 和 `CNOT` 作業 Q# ：</span><span class="sxs-lookup"><span data-stu-id="42ae1-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="42ae1-130">回報的計量</span><span class="sxs-lookup"><span data-stu-id="42ae1-130">Metrics Reported</span></span>

<span data-ttu-id="42ae1-131">資源估算器會追蹤下列計量：</span><span class="sxs-lookup"><span data-stu-id="42ae1-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="42ae1-132">計量</span><span class="sxs-lookup"><span data-stu-id="42ae1-132">Metric</span></span>|<span data-ttu-id="42ae1-133">描述</span><span class="sxs-lookup"><span data-stu-id="42ae1-133">Description</span></span>|
|----|----|
|<span data-ttu-id="42ae1-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="42ae1-134">__CNOT__</span></span>    |<span data-ttu-id="42ae1-135">作業的執行計數 `CNOT` (也稱為受控 Pauli X 作業) 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="42ae1-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="42ae1-136">__QubitClifford__</span></span> |<span data-ttu-id="42ae1-137">任何單一量子位 Clifford 和 Pauli 作業的執行計數。</span><span class="sxs-lookup"><span data-stu-id="42ae1-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="42ae1-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="42ae1-138">__Measure__</span></span>    |<span data-ttu-id="42ae1-139">任何測量的執行計數。</span><span class="sxs-lookup"><span data-stu-id="42ae1-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="42ae1-140">__R__</span><span class="sxs-lookup"><span data-stu-id="42ae1-140">__R__</span></span>    |<span data-ttu-id="42ae1-141">任何單一量子位旋轉、排除 `T` 、Clifford 和 Pauli 作業的執行計數。</span><span class="sxs-lookup"><span data-stu-id="42ae1-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="42ae1-142">__T__</span><span class="sxs-lookup"><span data-stu-id="42ae1-142">__T__</span></span>    |<span data-ttu-id="42ae1-143">作業的執行計數 `T` 和其 conjugates，包括 `T` 作業、T_x = .h 和 T_y = Hy Hy。</span><span class="sxs-lookup"><span data-stu-id="42ae1-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="42ae1-144">__Depth__</span><span class="sxs-lookup"><span data-stu-id="42ae1-144">__Depth__</span></span>|<span data-ttu-id="42ae1-145">作業所執行的量子線路深度下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="42ae1-146">根據預設，深度度量只會計算網 `T` 關。</span><span class="sxs-lookup"><span data-stu-id="42ae1-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="42ae1-147">如需詳細資訊，請參閱 [深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="42ae1-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="42ae1-148">__寬度__</span><span class="sxs-lookup"><span data-stu-id="42ae1-148">__Width__</span></span>    |<span data-ttu-id="42ae1-149">作業執行期間所配置的最大量子位數目下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="42ae1-150">可能無法同時達成 __深度__ 和 __寬度__ 下限。</span><span class="sxs-lookup"><span data-stu-id="42ae1-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="42ae1-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="42ae1-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="42ae1-152">在作業內借用的量子位數目上限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="42ae1-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="42ae1-153">提供測量結果的機率</span><span class="sxs-lookup"><span data-stu-id="42ae1-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="42ae1-154">您可以 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 從 <xref:microsoft.quantum.diagnostics> 命名空間使用，以提供有關測量運算之預期機率的資訊。</span><span class="sxs-lookup"><span data-stu-id="42ae1-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="42ae1-155">如需詳細資訊，請參閱[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器</span><span class="sxs-lookup"><span data-stu-id="42ae1-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="42ae1-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42ae1-156">See also</span></span>

- [<span data-ttu-id="42ae1-157">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="42ae1-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="42ae1-158">量子 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="42ae1-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="42ae1-159">量子完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="42ae1-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 