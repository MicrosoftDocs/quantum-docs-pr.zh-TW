---
title: 量子開發工具組資源估計工具 |Microsoft Docs
description: Microsoft 的量子開發工具組資源估計工具
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184979"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="be266-103">ResourcesEstimator 目的電腦</span><span class="sxs-lookup"><span data-stu-id="be266-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="be266-104">正如其名，`ResourcesEstimator` 會估計在量子電腦上執行 Q # 作業的指定實例所需的資源。</span><span class="sxs-lookup"><span data-stu-id="be266-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="be266-105">它會執行量子作業，而不實際模擬量子電腦的狀態，來完成這項操作;基於這個理由，它可以估計使用數千個 qubits 的 Q # 作業資源。</span><span class="sxs-lookup"><span data-stu-id="be266-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="be266-106">用量</span><span class="sxs-lookup"><span data-stu-id="be266-106">Usage</span></span>

<span data-ttu-id="be266-107">`ResourcesEstimator` 只是另一種類型的目的電腦，因此可以用來執行任何 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="be266-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="be266-108">作為其他目的電腦，若要在C#主機程式上使用它，請建立實例，並將它當做作業 `Run` 方法的第一個參數來傳遞：</span><span class="sxs-lookup"><span data-stu-id="be266-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="be266-109">如範例所示，`ResourcesEstimator` 會提供 `ToTSV()` 的方法，以產生可儲存在檔案中或寫入主控台進行分析的索引標籤分隔值（TSV）的資料表。</span><span class="sxs-lookup"><span data-stu-id="be266-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="be266-110">上述程式的輸出看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="be266-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="be266-111">`ResourcesEstimator` 不會在每次執行時重設其計算，如果使用相同的實例來執行另一個作業，則會將匯總計數保留在現有的結果上方。</span><span class="sxs-lookup"><span data-stu-id="be266-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="be266-112">如果您需要重設執行之間的計算，請在每次執行時建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="be266-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="be266-113">以程式設計方式抓取估計的資料</span><span class="sxs-lookup"><span data-stu-id="be266-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="be266-114">除了 TSV 資料表以外，您也可以透過 `ResourcesEstimator`的 `Data` 屬性，以程式設計方式抓取估計的資源。</span><span class="sxs-lookup"><span data-stu-id="be266-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="be266-115">`Data` 提供具有兩個數據行的 `System.DataTable` 實例： `Metric` 和 `Sum`，並根據計量名稱編制索引。</span><span class="sxs-lookup"><span data-stu-id="be266-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="be266-116">下列程式碼示範如何抓取和列印 Q # 作業所使用的 `QubitClifford`、`T` 和 `CNOT` 閘道總數：</span><span class="sxs-lookup"><span data-stu-id="be266-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="be266-117">回報的計量</span><span class="sxs-lookup"><span data-stu-id="be266-117">Metrics Reported</span></span>

<span data-ttu-id="be266-118">以下是 `ResourcesEstimator`所估計的計量清單：</span><span class="sxs-lookup"><span data-stu-id="be266-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="be266-119">__Cnot-contains__：執行的 cnot-contains （也稱為受控制的 Pauli X 閘道）的計數。</span><span class="sxs-lookup"><span data-stu-id="be266-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="be266-120">__QubitClifford__：執行的任何單一 qubit Clifford 和 Pauli 閘道的計數。</span><span class="sxs-lookup"><span data-stu-id="be266-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="be266-121">__Measure__：任何已執行之測量的計數。</span><span class="sxs-lookup"><span data-stu-id="be266-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="be266-122">__R__：任何執行的單一 qubit 輪替計數，不包括 T、Clifford 和 Pauli 閘道。</span><span class="sxs-lookup"><span data-stu-id="be266-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="be266-123">__T__： t 閘道和其 conjugates 的計數，包括 t 閘道、T_x = .h 和 T_y = Hy Hy、執行。</span><span class="sxs-lookup"><span data-stu-id="be266-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="be266-124">__深度__： Q # 作業所執行的量子線路深度。</span><span class="sxs-lookup"><span data-stu-id="be266-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="be266-125">根據預設，只有 T 閘道會在深度中計算，請參閱[深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="be266-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="be266-126">__寬度__：在 Q # 作業執行期間配置的最大 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="be266-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="be266-127">__BorrowedWidth__：在 Q # 作業內借用的 qubits 數目上限。</span><span class="sxs-lookup"><span data-stu-id="be266-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="be266-128">提供測量結果的機率</span><span class="sxs-lookup"><span data-stu-id="be266-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="be266-129"><xref:microsoft.quantum.primitive> 命名空間中的 <xref:microsoft.quantum.primitive.assertprob> 可用來提供測量預期機率的相關資訊，以協助驅動 Q # 程式的執行。</span><span class="sxs-lookup"><span data-stu-id="be266-129"><xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="be266-130">下列範例會加以說明：</span><span class="sxs-lookup"><span data-stu-id="be266-130">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="be266-131">當 `ResourcesEstimator` 遇到 `AssertProb` 會記錄在 `source` 上測量 `PauliZ`，而 `ancilla` 應獲得 `Zero` 的結果，機率為0.5。</span><span class="sxs-lookup"><span data-stu-id="be266-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="be266-132">當它在稍後執行 `M` 時，會發現結果機率的記錄值，而 `M` 會傳回 `Zero` 或 `One`，機率為0.5。</span><span class="sxs-lookup"><span data-stu-id="be266-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="be266-133">請參閱</span><span class="sxs-lookup"><span data-stu-id="be266-133">See also</span></span>

<span data-ttu-id="be266-134">`ResourcesEstimator` 是以「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」為基礎，可提供更豐富的計量集、在完整呼叫圖形上報告計量的能力，以及「[相異輸入檢查](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)」之類的功能，以協助找出問 # 程式上的錯誤。</span><span class="sxs-lookup"><span data-stu-id="be266-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="be266-135">如需詳細資訊，請參閱[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器檔。</span><span class="sxs-lookup"><span data-stu-id="be266-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

