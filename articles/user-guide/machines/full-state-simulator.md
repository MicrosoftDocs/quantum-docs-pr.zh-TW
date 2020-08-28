---
title: 完整狀態量子模擬器-量子開發工具組
description: 瞭解如何 Q# 在 Microsoft 量子開發工具組的完整狀態模擬器上執行您的程式。
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992212"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>量子開發工具組 (QDK) 完整狀態模擬器

QDK 會提供在本機電腦上模擬量子機器的完整狀態模擬器。 您可以使用完整狀態模擬器來執行和偵測以撰寫的量子演算法 Q# ，最多可利用30量子位。 完整狀態模擬器類似于 Microsoft Research  [LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) platform 中所使用的量子模擬器。

## <a name="invoking-and-running-the-full-state-simulator"></a>叫用和執行完整狀態模擬器

您可以透過類別公開完整狀態模擬器 `QuantumSimulator` 。 如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-simulator-from-c"></a>從 C 叫用模擬器#

建立類別的實例， `QuantumSimulator` 然後將它傳遞給量子作業的 `Run` 方法，以及任何其他參數。
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

由於類別會實 `QuantumSimulator` 作為 <xref:System.IDisposable> 介面，因此當您不再需要模擬器的實例時，您必須呼叫 `Dispose` 方法。 若要這麼做，最好的方法就是在 [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) 語句內包裝模擬器宣告和作業，這會自動呼叫 `Dispose` 方法。

### <a name="invoking-the-simulator-from-python"></a>從 Python 叫用模擬器

使用已匯入作業的 Python 程式庫中的 [模擬 ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# Q# ：

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>從命令列叫用模擬器

Q#從命令列執行程式時，完整狀態模擬器是預設的目的電腦。 （選擇性）您可以使用 **--** 模擬器 (或 **-s** 快速鍵) 參數來指定所需的目的電腦。 下列兩個命令都會使用完整狀態模擬器來執行程式。 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>從 Juptyer 筆記本叫用模擬器

使用 I Q# 魔術命令 [% 模擬](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 來執行 Q# 操作。

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>植入模擬器

根據預設，完整狀態模擬器會使用亂數產生器來模擬量子隨機性。 基於測試目的，有決定性的結果有時會很有用。 在 c # 程式中，您可以透過參數在函式中提供亂數產生器的種子來完成這項操作 `QuantumSimulator` `randomNumberGeneratorSeed` 。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>設定執行緒

完整狀態模擬器會使用 [OpenMP](http://www.openmp.org/) 將所需的線性代數平行化。 根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位的程式通常執行速度很慢，因為所需的協調 dwarfs 實際工作。 您可以藉由將環境變數設定 `OMP_NUM_THREADS` 為較小的數位來修正此問題。 根據經驗法則，請針對最多四個量子位設定一個執行緒，然後針對每個量子位設定一個額外的執行緒。 您可能需要根據您的演算法調整變數。

## <a name="see-also"></a>另請參閱

- [量子資源估算器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)