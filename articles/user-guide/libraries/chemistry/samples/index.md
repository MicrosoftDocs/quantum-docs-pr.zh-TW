---
title: 量子化學範例應用程式
description: 探索 Microsoft 量子化學程式庫的範例應用程式。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273384"
---
# <a name="quantum-chemistry-examples"></a>量子化學範例

在量子化學概念中，我們手動建立了範例費米子 Hamiltonian。 現在，我們將結合[模擬 Hamiltonian 力學](xref:microsoft.quantum.libraries.standard.algorithms)中所述的化學模擬演算法與 Canon 程式庫中[量子階段估算](xref:microsoft.quantum.libraries.characterization)。 這種組合可讓我們在代表的分子中取得能階的估計值，這是量子電腦上的量子化學其中的一項主要應用。 

我們也會依照一些範例逐步大規模地執行量子化學實驗，而不是逐一說明 Hamiltonian 的詞彙。 首先我們要參考的範例，會載入以 [Broombridge 結構描述](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)編碼的化學 Hamiltonian。

對於過大而無法在[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)上模擬的分子，我們仍可執行有趣的科學實驗。 例如，我們仍可以[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)為目標，來評估執行大型化學模擬的資源成本。

接著，我們就要透過幾個既有的範例，來了解化學模擬程式庫的有趣應用。
