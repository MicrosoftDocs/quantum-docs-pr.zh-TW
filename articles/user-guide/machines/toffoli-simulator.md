---
title: 量子開發工具組 Toffoli 模擬器
description: 深入瞭解 Microsoft QDK Toffoli 模擬器，這是一種特殊用途的量子模擬器，可與數百萬個 qubits 搭配使用。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274680"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>量子開發工具組 Toffoli 模擬器

配量開發工具組提供 Toffoli 模擬器，這是一種特殊用途的模擬器，可以模擬僅限於 X、CNOT-CONTAINS 和多重控制 X 配量作業的配量演算法（所有傳統邏輯和計算皆可使用）。

雖然 Toffoli 模擬器比[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但它可以模擬遠較多的 qubits。
Toffoli 模擬器可以與數百萬個 qubits 搭配使用，而完整狀態模擬器通常限制為大約30個。
它可以執行並在您的電腦上，以 Q # 撰寫一組有限的量子演算法，比方說，評估布耳函數的 oracles 可以使用這些閘道來執行，因此在上測試時，會使用此模擬器來改變大量的 qubits。

此配量模擬器會透過 `ToffoliSimulator` 類別公開。
若要使用模擬器，請直接建立此類別的實例，並將它傳遞給 `Run` 您想要執行的量子作業方法，以及其餘的參數：

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>其他作業

`ToffoliSimulator` `R` 當產生的作業 `Exp` 等於或到身分識別時，支援旋轉和 exponentiated Paulis （例如和） `X` 。

測量和判斷提示受到支援，但只能以 Pauli 為 `Z` 基礎。
請注意，某些測量的機率一律為0或 1;Toffoli 模擬器中沒有隨機性。

`DumpMachine``DumpRegister`支援和。
它們都會輸出 `Z` 每個 qubit 的目前基礎狀態，每行一個 qubit。

## <a name="qubitcount"></a>QubitCount

根據預設，會 `ToffoliSimulator` 為 65536 qubits 配置空間。
如果您的演算法需要的不只是這種情況，您可以將參數的值提供給函式，藉以變更 qubit 計數 `qubitCount` 。
每個額外的 qubit 都需要額外的記憶體位元組，因此高估您需要的 qubits 數目並不會有重大成本。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
