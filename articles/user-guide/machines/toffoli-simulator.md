---
title: 量子 Toffoli 模擬器-量子開發工具組
description: 深入瞭解 Microsoft QDK Toffoli 模擬器，這是一種特殊用途的量子模擬器，可與數百萬個 qubits 搭配使用。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8a981645703423856e667be7c3dccf5270a5885f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868095"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a> (QDK) Toffoli 模擬器的量子開發工具組

QDK Toffoli 模擬器是一個特殊用途的模擬器，具有有限的範圍，而且只支援 `X` 、 `CNOT` 和多個控制的 `X` 量子作業。 所有的傳統邏輯和計算都可供使用。

雖然 Toffoli 模擬器的功能比[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但它的優點是能夠模擬更多 qubits。 Toffoli 模擬器可以與數百萬個 qubits 搭配使用，而完整狀態模擬器則限制為大約 30 qubits。 例如，這對於評估布耳函數的 oracles 來說很有用-它們可以使用有限的支援演算法集來實行，並在大量的 qubits 上進行測試。

## <a name="invoking-the-toffoli-simulator"></a>叫用 Toffoli 模擬器

您會透過類別公開 Toffoli 模擬器 `ToffoliSimulator` 。 如需其他詳細資訊，請參閱[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-toffoli-simulator-from-c"></a>從 C 叫用 Toffoli 模擬器#

就像其他目標機器一樣，您必須先建立 `ToffoliSimulator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。

請注意，不同於 `QuantumSimulator` 類別，`ToffoliSimulator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>從 Python 叫用 Toffoli 模擬器

使用來自 Python 程式庫的[toffoli_simulate ( # B1](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法和匯入的作業 Q# ：

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>從命令列叫用 Toffoli 模擬器

Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s**快捷方式) 參數來指定 Toffoli 模擬器目的電腦。 下列命令會使用 [資源] 估計工具來執行程式： 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>從 Juptyer 筆記本叫用 Toffoli 模擬器

使用 I Q# 魔術命令[% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)來執行此作業 Q# 。

```
%toffoli myOperation
```

## <a name="supported-operations"></a>支援的作業

Toffoli 模擬器支援：

* `R` `Exp` 當產生的作業等於或身分識別矩陣時，旋轉和 exponentiated Paulis （例如和） `X` 。
* 測量和判斷[提示作業，](xref:microsoft.quantum.diagnostics.assertmeasurement)但僅以 Pauli 為 `Z` 基礎。 請注意，測量運算的機率一律為**0**或**1**。Toffoli 模擬器中沒有隨機性。
* `DumpMachine`和 `DumpRegister` 函數。
這兩個函式都會輸出 `Z` 每個 qubit 的目前基礎狀態，每行一個 qubit。

## <a name="specifying-the-number-of-qubits"></a>指定 qubits 的數目

根據預設， `ToffoliSimulator` 實例會為 65536 qubits 配置空間。
如果您的演算法需要比這更多的 qubits，您可以將參數的值提供給函式，藉以指定 qubit 計數 `qubitCount` 。
每個額外的 qubit 只需要一個位元組的記憶體，因此高估您需要的 qubits 數目並不會有重大的成本。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>另請參閱

- [量子資源估計工具](xref:microsoft.quantum.machines.resources-estimator)
- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 