---
title: 量子開發工具組資源估計工具
description: '深入瞭解資源估計工具，其會估計在量子電腦上執行 Q # 作業的指定實例所需的資源。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 37c901e5a861f0e8a10cdc911ad1d84ddd3e6e00
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907047"
---
# <a name="the-resourcesestimator-target-machine"></a>ResourcesEstimator 目的電腦

正如其名，`ResourcesEstimator` 會估計在量子電腦上執行 Q # 作業的指定實例所需的資源。
它會執行量子作業，而不實際模擬量子電腦的狀態，來完成這項操作;基於這個理由，它可以估計使用數千個 qubits 的 Q # 作業資源。

## <a name="usage"></a>使用量

`ResourcesEstimator` 只是另一種類型的目的電腦，因此可以用來執行任何 Q # 作業。 

作為其他目的電腦，若要在C#主機程式上使用它，請建立實例，並將它當做作業 `Run` 方法的第一個參數來傳遞：

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

如範例所示，`ResourcesEstimator` 會提供 `ToTSV()` 的方法，以產生可儲存在檔案中或寫入主控台進行分析的索引標籤分隔值（TSV）的資料表。 上述程式的輸出看起來應該像這樣：

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
> `ResourcesEstimator` 不會在每次執行時重設其計算，如果使用相同的實例來執行另一個作業，則會將匯總計數保留在現有的結果上方。
> 如果您需要重設執行之間的計算，請在每次執行時建立新的實例。


## <a name="programmatically-retrieving-the-estimated-data"></a>以程式設計方式抓取估計的資料

除了 TSV 資料表以外，您也可以透過 `ResourcesEstimator`的 `Data` 屬性，以程式設計方式抓取估計的資源。 `Data` 提供具有兩個數據行的 `System.DataTable` 實例： `Metric` 和 `Sum`，並根據計量名稱編制索引。

下列程式碼示範如何抓取和列印 Q # 作業所使用的 `QubitClifford`、`T` 和 `CNOT` 閘道總數：

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

## <a name="metrics-reported"></a>回報的計量

以下是 `ResourcesEstimator`所估計的計量清單：

* __Cnot-contains__：執行的 cnot-contains （也稱為受控制的 Pauli X 閘道）的計數。
* __QubitClifford__：執行的任何單一 qubit Clifford 和 Pauli 閘道的計數。
* __Measure__：任何已執行之測量的計數。
* __R__：任何執行的單一 qubit 輪替計數，不包括 T、Clifford 和 Pauli 閘道。
* __T__： t 閘道和其 conjugates 的計數，包括 t 閘道、T_x = .h 和 T_y = Hy Hy、執行。
* __深度__： Q # 作業所執行的量子線路深度。 根據預設，只有 T 閘道會在深度中計算，請參閱[深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)以取得詳細資料。
* __寬度__：在 Q # 作業執行期間配置的最大 qubits 數目。
* __BorrowedWidth__：在 Q # 作業內借用的 qubits 數目上限。


## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

<xref:microsoft.quantum.intrinsic> 命名空間中的 <xref:microsoft.quantum.intrinsic.assertprob> 可用來提供測量預期機率的相關資訊，以協助驅動 Q # 程式的執行。 下列範例會加以說明：

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

當 `ResourcesEstimator` 遇到 `AssertProb` 會記錄在 `source` 上測量 `PauliZ`，而 `q` 應獲得 `Zero` 的結果，機率為0.5。 當它在稍後執行 `M` 時，會發現結果機率的記錄值，而 `M` 會傳回 `Zero` 或 `One`，機率為0.5。


## <a name="see-also"></a>另請參閱

`ResourcesEstimator` 是以「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」為基礎，可提供更豐富的計量集、在完整呼叫圖形上報告計量的能力，以及「[相異輸入檢查](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)」之類的功能，以協助找出問 # 程式上的錯誤。 如需詳細資訊，請參閱[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器檔。

