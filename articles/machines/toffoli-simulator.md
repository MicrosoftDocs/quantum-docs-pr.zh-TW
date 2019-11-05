---
title: 量子開發工具組 Toffoli 模擬器 |Microsoft Docs
description: Microsoft 的量子開發工具組 Toffoli 模擬器總覽
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442361"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>量子開發工具組 Toffoli 模擬器

配量開發工具組提供 Toffoli 模擬器，這是一種特殊用途的模擬器，可以模擬僅限於 X、CNOT-CONTAINS 和多重控制 X 配量作業的配量演算法（所有傳統邏輯和計算皆可使用）。

雖然 Toffoli 模擬器比[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但它可以模擬遠較多的 qubits。
Toffoli 模擬器可以與數百萬個 qubits 搭配使用，而完整狀態模擬器通常限制為大約30個。
它可以執行並在您的電腦上，以 Q # 撰寫一組有限的量子演算法，比方說，評估布耳函數的 oracles 可以使用這些閘道來執行，因此在上測試時，會使用此模擬器來改變大量的 qubits。

這個量子模擬器會透過 `ToffoliSimulator` 類別公開。
若要使用模擬器，請直接建立此類別的實例，並將它傳遞給您想要執行之量子作業的 `Run` 方法，以及其餘的參數：

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>其他作業

當產生的作業等於 `X` 或身分識別時，`ToffoliSimulator` 支援旋轉和 exponentiated Paulis，例如 `R` 和 `Exp`。

測量和判斷提示受到支援，但僅限在 Pauli `Z` 基礎中。
請注意，某些測量的機率一律為0或 1;Toffoli 模擬器中沒有隨機性。

支援 `DumpMachine` 和 `DumpRegister`。
它們都會輸出每個 qubit 的目前 `Z`基礎狀態，每行一個 qubit。

## <a name="qubitcount"></a>QubitCount

根據預設，`ToffoliSimulator` 會為 65536 qubits 配置空間。
如果您的演算法需要的不只是這種情況，您可以藉由將 `qubitCount` 參數的值提供給此函式來變更 qubit 計數。
每個額外的 qubit 都需要額外的記憶體位元組，因此高估您需要的 qubits 數目並不會有重大成本。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
