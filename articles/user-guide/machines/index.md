---
title: 量子模擬器和 Q# 程式
description: 說明可做為 Q# 程式目標機器的量子模擬器。
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858775"
---
# <a name="quantum-simulators"></a>量子模擬器

量子模擬器是可在傳統電腦上執行的軟體程式，能做為 Q# 程式的「目標機器」，可讓您在會預測量子位元將如何回應不同運算的環境中執行和測試量子程式。 本文說明 Quantum 開發套件 (QDK) 中包含哪些量子模擬器，以及將 Q# 程式傳遞至量子模擬器的不同方式，例如透過命令列或使用以傳統語言撰寫的驅動程式程式碼。  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Quantum 開發套件 (QDK) 量子模擬器

量子模擬器負責為演算法提供量子基元的實作。 這包括基元操作 (例如 `H`、`CNOT`、`Measure`) 以及量子位元的管理和追蹤。 QDK 包含不同的量子模擬器類別，代表模擬相同量子演算法的不同方式。 


每種量子模擬器都可以針對這些基元提供不同的實作。 例如，[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)會藉由完全模擬[量子狀態向量](xref:microsoft.quantum.glossary#quantum-state)來執行量子演算法，而[量子電腦追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)根本不會考慮實際的量子狀態。 相反地，該模擬器會追蹤該演算法的量子閘、量子位元和其他資源使用狀況。

### <a name="quantum-machine-classes"></a>量子機器類別

在未來，QDK 將定義其他量子機器類別，以支援其他類型的模擬，以及支援在量子硬體上執行。 讓演算法可以在改變基礎機器實作的情況下保持不變，您就可以輕鬆地在模擬中測試演算法並進行偵錯，然後再於真正的硬體上執行，因為您知道演算法並未改變。

QDK 包含數個量子機器類別，全都定義在 `Microsoft.Quantum.Simulation.Simulators` 命名空間中。

|模擬器 |類別|描述|
|-----|------|---|
|[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | 執行和偵錯量子演算法，而且限制為大約 30 個量子位元。 |
|[簡單資源估算器](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | 對執行量子演算法所需的資源執行最高層級的分析，可支援數千個量子位元。|
|[追蹤型資源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |針對演算法的整個呼叫圖執行資源耗用量的進階分析，可支援數千個量子位元。|
|[Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |模擬的量子演算法僅限於 `X`、`CNOT`、多重控制 `X` 量子作業，可支援百萬個量子位元。 |

## <a name="invoking-the-quantum-simulator"></a>叫用量子模擬器

在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中，會示範三種將 Q# 程式碼傳遞至量子模擬器的方式： 

* 使用命令列
* 使用 Python 主機程式
* 使用 C# 主機程式

量子機器是一般 .NET 類別的執行個體，因此可藉由叫用其建構函式來加以建立，就和任何 .NET 類別一樣。 執行此動作的方式取決於您執行 Q# 程式的方式。

## <a name="next-steps"></a>後續步驟

* 如需如何在不同環境中的 Q# 程式叫用目標機器的詳細資訊，請參閱 [ 種方式來執行 Q# 程式 ](xref:microsoft.quantum.guide.host-programs)。
