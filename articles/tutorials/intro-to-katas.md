---
title: Quantum Katas 簡介
description: 了解 Microsoft Quantum Development Kit (QDK) 所提供的 Katas (訓練練習)
author: bradben
ms.author: v-benbra
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6b2eff2a457b809bd168b9b59ab013b7fc7541e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691650"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>透過 Quantum Katas 學習量子運算

[量子 Katas](https://github.com/Microsoft/QuantumKatas/) 是開放原始碼、自學式的教學課程和程式設計練習，旨在以同時教學量子運算和程式設計的元素 Q# 。

## <a name="learning-by-doing"></a>邊做邊學

本專案中收集的教學課程和練習強調藉由執行來學習，提供的程式設計任務涵蓋了從極簡單到極具挑戰的特定主題。 每項任務工作都需要您填寫一些程式碼；第一個任務工作可能只需要一行，之後的任務工作則可能需要很大一段程式碼。

最重要的是，Katas 包括可設定、執行、驗證的任務工作解決方案的測試架構。 這可讓您立即得到對解決方案的意見反應，並在不正確的情況下重新考慮您的做法。

您可以在自選環境中使用：

* 在 Binder 環境中的線上 Jupyter Notebook
* 在本機電腦上執行的 Jupyter Notebook
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>使用 Quantum Katas 能學到什麼？

探索量子運算的基本概念和基礎，或深入了解量子演算法和通訊協定。 我們建議您一開始先遵循此學習路徑，以確保您能夠充分瞭解量子運算的基本概念。 當然，您可以略過您已熟悉的主題 (例如複雜的算術)，並依您想要的任何順序學習演算法。

### <a name="introduction-to-quantum-computing-concepts"></a>量子運算概念簡介

| Kata | 描述 |
|:-----|-------------|
|[複雜算術](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)|本教學課程說明處理量子運算所需的一些數學背景，例如虛數和複數。|
|[線性代數](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)|線性代數是用來代表量子運算中的配量狀態和作業。 本教學課程涵蓋基本概念，包括矩陣和向量。|
|[量子位元概念](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/Qubit)|深入了解量子位元，這是量子運算的其中一個核心概念。 |
|[單一量子位元的量子閘](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates)|本教學課程介紹單一量子位元的量子閘，其可作為量子演算法的建構元素，並以各種方式轉換量子的量子位元狀態。|
|[多 qubit 系統](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitSystems)|本教學課程介紹多量子位系統、其在數學標記法和程式碼中的標記法 Q# ，以及纏結的概念。|
|[多量子位元的量子閘](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitGates)|本教學課程遵循[單一量子位元的量子閘](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates)教學課程，並著重於將量子閘套用至多量子位元系統。|

### <a name="quantum-computing-fundamentals"></a>量子運算基本概念

| Kata | 描述 |
|:-----|-------------|
|[辨識量子閘](https://github.com/microsoft/QuantumKatas/tree/main/BasicGates)|一系列的練習，旨在讓您熟悉中的基本量子閘道 Q# 。 包括適用於基本單一量子位元和多量子位元量子閘的練習、伴隨和控制的量子閘，以及如何使用量子閘來修改量子位元的狀態。|
|[建立量子疊加](https://github.com/microsoft/QuantumKatas/tree/main/Superposition)|使用這些練習，熟悉中的迭加和程式設計概念 Q# 。 包含在中進行基本單一量子位和多量子位閘道、迭加和流程式控制制和遞迴的練習 Q# 。|
|[使用測量來區別量子狀態](https://github.com/microsoft/QuantumKatas/tree/main/Measurements)|請解決這些練習，了解量子測量和正交與非正交狀態。 |
|[聯結測量](https://github.com/microsoft/QuantumKatas/tree/main/JointMeasurements)|了解聯合同位測量，以及如何使用[量值](xref:Microsoft.Quantum.Intrinsic.Measure)作業來區別量子狀態。|

### <a name="algorithms"></a>演算法

| Kata | 描述 |
|:-----|-------------|
|[量子遙傳](https://github.com/microsoft/QuantumKatas/tree/main/Teleportation)|此 kata 會探索量子遙傳，這是一種通訊協定，允許只使用傳統通訊和先前共用的量子糾纏來傳達量子狀態。|
|[密集編碼](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)|密集編碼是一種通訊協定，可透過使用先前共用的量子糾纏只傳送一個量子位元，來傳輸兩個位元的傳統資訊。  |
|[Deutsch – Jozsa 演算法](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringDeutschJozsaAlgorithm)|這個演算法非常著名，因為該演算法是量子演算法的第一個範例，其速度比任何具決定性的傳統演算法更快。|
|[探索格羅弗搜尋演算法的高階屬性](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringGroversAlgorithm)|量子運算中最著名演算法之一的高階簡介。 解決了尋找會產生特定輸出的黑箱 (Oracle) 輸入的問題。 |
|[實作格羅弗搜尋演算法](https://github.com/microsoft/QuantumKatas/tree/main/GroversAlgorithm)|這個 kata 更深入探討格羅弗搜尋演算法，並涵蓋撰寫 Oracle、執行演算法的步驟，最後將其全部放在一起。|
|[使用格羅弗演算法解決真正的問題：SAT 問題](https://github.com/microsoft/QuantumKatas/tree/main/SolveSATWithGrover)|一系列使用格羅弗演算法的練習，使用[布林值可滿足性問題](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) 作為範例，解決實際的問題。  |
|[使用格羅弗演算法解決真正的問題：圖形著色問題](https://github.com/microsoft/QuantumKatas/tree/main/GraphColoring)| 這個 kata 進一步探索格羅弗演算法，這次使用圖形著色問題作為範例，解決[條件約束滿意度](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)問題。 |

### <a name="protocols-and-libraries"></a>通訊協定和程式庫

| Kata | 描述 |
|:-----|-------------|
|[用於量子索引碼散發的 BB84 通訊協定](https://github.com/microsoft/QuantumKatas/tree/main/KeyDistribution_BB84)|深入了解並實作量子金鑰散佈通訊協定 [BB84](https://en.wikipedia.org/wiki/BB84)，使用量子位元來交換密碼編譯金鑰。 |
|[位元翻轉糾錯碼](https://github.com/microsoft/QuantumKatas/tree/main/QEC_BitFlipCode)|使用最簡單的量子量子錯誤修正 (QEC) 程式碼 (三個量子位元的位元翻轉程式碼) 來探索量子錯誤修正。|
|[相位估算法](https://github.com/microsoft/QuantumKatas/blob/main/PhaseEstimation)|相位估計演算法是一些最基本的量子運算建構元素。 透過這些練習瞭解階段估計，這些練習涵蓋了量子階段估計，以及如何準備和執行中的階段估計常式 Q# 。|
|[量子算術：建立脈動進位加法器](https://github.com/microsoft/QuantumKatas/blob/main/RippleCarryAdder)|探索量子電腦上[脈動進位](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder)加法的系列深入練習。 建立就地量子加法器、使用不同的演算法加以擴充，最後建立就地量子減法器。   |

### <a name="entanglement-games"></a>纏結遊戲

| Kata | 描述 |
|:-----|-------------|
|[CHSH 遊戲](https://github.com/microsoft/QuantumKatas/tree/main/CHSHGame)|利用 [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality) 遊戲的實作，探索量子糾纏。 這個[非本機](https://en.wikipedia.org/wiki/Quantum_refereed_game)遊戲會示範可以如何使用量子糾纏，來增加玩家超越純粹傳統策略可能的獲勝機會。|
|[GHZ 遊戲](https://github.com/microsoft/QuantumKatas/tree/main/GHZGame)|GHZ 遊戲是另一個非本機遊戲，但是牽涉到三個玩家。|
|[Mermin-Peres 魔術方塊遊戲](https://github.com/microsoft/QuantumKatas/tree/main/MagicSquareGame)|探索[量子虛擬遙測](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game)以解決魔術方陣遊戲的一系列練習。  |

## <a name="resources"></a>資源

查看全系列的 [Quantum Katas](https://github.com/microsoft/QuantumKatas)

[線上執行 Katas](https://aka.ms/try-quantum-katas)
