---
title: 完整狀態模擬器
description: '瞭解如何在 Microsoft Quantum Development Kit 完整狀態模擬器上執行您的 Q # 程式。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906112"
---
# <a name="quantum-development-kit-full-state-simulator"></a>量子開發工具組完整狀態模擬器

配量開發工具組提供的完整狀態配量模擬器，類似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 。
此模擬器可用來執行和偵錯工具中以 Q # 撰寫的量子演算法。

這個量子模擬器會透過 `QuantumSimulator` 類別公開。 若要使用模擬器，請直接建立此類別的實例，並將它傳遞給您想要執行之量子作業的 `Run` 方法，以及其餘的參數：

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator` 類別會執行 <xref:System.IDisposable>，因此一旦模擬器的實例不再使用，就應該呼叫 `Dispose` 方法。 執行這項操作的最佳方式是將模擬器包裝在 `using` 語句中，如上述範例所示。

## <a name="seed"></a>Seed

`QuantumSimulator` 使用亂數產生器來模擬量子隨機性。 基於測試目的，有決定性的結果有時會很有用。 這可以藉由在 `QuantumSimulator`的程式碼中透過 `randomNumberGeneratorSeed` 參數提供亂數產生器的種子來完成：

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

`QuantumSimulator` 使用[OpenMP](http://www.openmp.org/)來平行處理所需的線性代數。 根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。 將環境變數 `OMP_NUM_THREADS` 設定為較小的數位，即可修正此問題。 一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。

