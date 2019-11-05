---
title: Quantum Katas 簡介
description: 了解 Microsoft Quantum Development Kit (QDK) 所提供的 Katas (訓練練習)
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444135"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>透過 Quantum Katas 學習量子運算

[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) 是開放原始碼的集合，包括自學型教學課程和程式設計練習，目標是要同時讓您學會量子運算和 Q# 程式設計的要素。

## <a name="learning-by-doing"></a>邊做邊學

本專案中收集的教學課程和 Katas 強調藉由執行來學習，提供的程式設計任務涵蓋了從極簡單到極具挑戰的特定主題。 每項任務工作都需要您填寫一些程式碼；第一個任務工作可能只需要一行，之後的任務工作則可能需要很大一段程式碼。

最重要的是，Katas 包括可設定、執行、驗證的任務工作解決方案的測試架構。 這可讓您立即得到對解決方案的意見反應，並在不正確的情況下重新考慮您的做法。

您可以在自選環境中使用：

* 在 Binder 環境中的線上 Jupyter Notebook
* 在本機電腦上執行的 Jupyter Notebook
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>使用 Quantum Katas 能學到什麼？

以下摘要 Quantum Katas 所涵蓋的主要主題。 我們建議您一開始先遵循此學習路徑，以確保您能夠充分瞭解量子運算的基本概念。 當然，您可以略過您已熟悉的主題 (例如複雜的算術)，並依您想要的任何順序學習演算法。

### <a name="introduction-to-quantum-computing-concepts"></a>量子運算概念簡介

* [複雜算術](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [線性代數](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [量子位元概念](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [單一量子位元的量子閘](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>量子運算基本概念

* [辨識量子閘](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [建立量子疊加](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [使用測量來區別量子狀態](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [聯結測量](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>演算法

* [量子遙傳](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [密集編碼](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch – Jozsa 演算法](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [實作格羅弗搜尋演算法](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [探索格羅弗搜尋演算法的高階屬性](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* 使用格羅弗演算法解決真正的問題：[SAT 問題](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover)和[圖形著色問題](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>通訊協定和程式庫

* [用於量子索引碼散發的 BB84 通訊協定](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* 量子錯誤更正：[位元翻轉糾錯碼](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [相位估算法](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* 量子算術：[建立脈動進位加法器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>纏結遊戲

* [CHSH 遊戲](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [GHZ 遊戲](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [Mermin-Peres 魔術方塊遊戲](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>資源

* 查看全系列的 [Quantum Katas](https://github.com/microsoft/QuantumKatas)
* [線上執行 Katas](https://aka.ms/try-quantum-katas)
