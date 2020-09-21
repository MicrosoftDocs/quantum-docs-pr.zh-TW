---
title: 量子 Toffoli 模擬器-量子開發工具組
description: 深入瞭解 Microsoft QDK Toffoli 模擬器，這是可用於數百萬個量子位的特殊用途量子模擬器。
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 82882f01d1b5c036faee71f18a18b2595107ddb7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835905"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>量子開發工具組 (QDK) Toffoli 模擬器

QDK Toffoli 模擬器是具有有限範圍的特殊用途模擬器，而且僅支援 `X` 、 `CNOT` 和多重控制的 `X` 量子作業。 所有傳統邏輯和計算都可供使用。

雖然 Toffoli 模擬器的功能比 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但是它的優點是能夠模擬更多量子位。 Toffoli 模擬器可用於數百萬個量子位，而完整狀態模擬器的限制為大約30個量子位。 這項功能很有用，例如，使用評估布林函式的 oracle 時，可以使用有限的支援演算法集來執行，並在大量的量子位上進行測試。

## <a name="invoking-the-toffoli-simulator"></a>叫用 Toffoli 模擬器

您可以透過類別公開 Toffoli 模擬器 `ToffoliSimulator` 。 如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-toffoli-simulator-from-c"></a>從 C 叫用 Toffoli 模擬器#

就像其他目標機器一樣，您必須先建立 `ToffoliSimulator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。

請注意，不同於 `QuantumSimulator` 類別，`ToffoliSimulator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>從 Python 叫用 Toffoli 模擬器

使用匯入作業，從 Python 程式庫使用 [toffoli_simulate ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>從命令列叫用 Toffoli 模擬器

Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s**快速鍵) 參數來指定 Toffoli 模擬器目的電腦。 下列命令會使用資源估算器來執行程式： 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>從 Juptyer 筆記本叫用 Toffoli 模擬器

使用 I Q# 魔術命令 [% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) 來執行 Q# 操作。

```
%toffoli myOperation
```

## <a name="supported-operations"></a>支援的作業

Toffoli 模擬器支援：

* `R` `Exp` 當產生的作業等於或識別矩陣時，旋轉和 exponentiated Paulis （例如和） `X` 。
* 量測 [和判斷提示作業，但](xref:microsoft.quantum.diagnostics.assertmeasurement) 僅限 Pauli `Z` 基礎。 請注意，測量運算的機率一律為 **0** 或 **1**;Toffoli 模擬器中沒有隨機性。
* `DumpMachine` 和函式 `DumpRegister` 。
這兩個函式都會輸出 `Z` 每個量子位的目前基礎狀態，每行一個量子位。

## <a name="specifying-the-number-of-qubits"></a>指定量子位的數目

根據預設， `ToffoliSimulator` 實例會為65536量子位配置空間。
如果您的演算法需要比這個更多的量子位，您可以提供參數的值給函式來指定量子位元數目 `qubitCount` 。
每個額外的量子位都只需要一個位元組的記憶體，因此高估您需要的量子位數量沒有任何重大成本。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>另請參閱

- [量子資源估算器](xref:microsoft.quantum.machines.resources-estimator)
- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 