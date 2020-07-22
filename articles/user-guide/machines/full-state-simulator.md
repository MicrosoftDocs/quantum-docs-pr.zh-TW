---
title: 完整狀態量子模擬器-量子開發工具組
description: '瞭解如何在 Microsoft Quantum Development Kit 完整狀態模擬器上執行您的 Q # 程式。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871173"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>量子開發工具組（QDK）完整狀態模擬器

QDK 提供的完整狀態模擬器會模擬您本機電腦上的量子機器。 您可以使用完整狀態模擬器來執行和調試以 Q # 撰寫的配量演算法，最多可達 30 qubits。 完整狀態模擬器類似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) platform 中使用的量子模擬器。

## <a name="invoking-and-running-the-full-state-simulator"></a>叫用和執行完整狀態模擬器

您可以透過類別公開完整狀態模擬器 `QuantumSimulator` 。 如需其他詳細資訊，請參閱[執行 Q # 程式的方式](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-simulator-from-c"></a>從 C 叫用模擬器#

建立類別的實例， `QuantumSimulator` 然後將它傳遞給量子作業的 `Run` 方法，以及任何其他參數。
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

因為類別會實 `QuantumSimulator` <xref:System.IDisposable> 作用介面，所以您必須在不再需要模擬器的 `Dispose` 實例後呼叫方法。 這麼做的最佳方式是在[using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement)語句中包裝模擬器宣告和作業，這會自動呼叫 `Dispose` 方法。

### <a name="invoking-the-simulator-from-python"></a>從 Python 叫用模擬器

使用來自 Q # Python 程式庫的[模擬（）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法，以及匯入的 Q # 操作：

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>從命令列叫用模擬器

從命令列執行 Q # 程式時，完整狀態模擬器是預設的目的電腦。 （選擇性）您可以使用 **--** 模擬器（或 **-s**快捷方式）參數來指定所需的目的電腦。 下列兩個命令都會使用完整狀態模擬器來執行程式。 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>從 Juptyer 筆記本叫用模擬器

使用 IQ # 魔術命令[% 模擬](xref:microsoft.quantum.iqsharp.magic-ref.simulate)來執行 Q # 作業。

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>植入模擬器

根據預設，完整狀態模擬器會使用亂數產生器來模擬量子隨機性。 基於測試目的，有決定性的結果有時會很有用。 在 c # 程式中，您可以藉由在函式中透過參數提供亂數字產生器的種子來完成這項操作 `QuantumSimulator` `randomNumberGeneratorSeed` 。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>設定執行緒

完整狀態模擬器會使用[OpenMP](http://www.openmp.org/)來平行處理所需的線性代數。 根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量 qubits 的程式通常會執行緩慢，因為所需的協調會 dwarfs 實際的工作。 您可以藉由將環境變數設定 `OMP_NUM_THREADS` 為較小的數位來修正此問題。 根據經驗法則，將一個執行緒設定為最多四個 qubits，然後針對每個 qubit 設定一個額外的執行緒。 視您的演算法而定，您可能需要調整變數。

## <a name="see-also"></a>請參閱

- [量子資源估計工具](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)