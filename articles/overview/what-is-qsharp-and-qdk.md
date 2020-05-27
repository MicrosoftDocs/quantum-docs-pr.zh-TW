---
title: Q# 程式設計語言和 QDK 是什麼？
description: 了解 Microsoft Quantum 開發套件、Q# 程式設計語言，以及要如何建立量子程式。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
ms.openlocfilehash: 55ac946aa935d3748b36ac99096a89d0db686835
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433022"
---
# <a name="what-are-the-q-programming-language-and-qdk"></a>Q# 程式設計語言和 QDK 是什麼？

Q# 是 Microsoft 的開放原始碼程式設計語言，可用來開發和執行量子演算法。 其屬於 Quantum 開發套件 (QDK) 的一部分，內含 [Q# 程式庫](xref:microsoft.quantum.libraries)、[量子模擬器](xref:microsoft.quantum.machines)、[適用於其他程式設計環境的擴充功能](xref:microsoft.quantum.install)和 [API 文件](xref:microsoft.quantum.standardlibsintro)。 除了標準的 Q# 程式庫之外，QDK 還包含化學、機器學習與數值程式庫。

作為程式設計語言，Q# 擷取了 Python、C# 和 F# 中的熟悉元素，並可支援使用迴圈、if/then 陳述式和常見資料類型來撰寫程式的基本程序模型。 其也引進了新的量子特有資料結構和運算。

## <a name="what-can-i-do-with-the-qdk"></a>QDK 有何用途？

QDK 是適用於 Q# 的完整功能開發套件，您可與常用的工具和語言搭配使用以便開發可在各種環境中執行的量子應用程式。 Q# 程式可作為命令列應用程式來執行、透過 Jupyter Notebook 來執行，也可以使用 Python 或 .NET 主機程式來執行。

### <a name="develop-in-common-tools-and-environments"></a>在常見的工具和環境中進行開發

請將量子開發與 [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone) 和 [Jupyter Notebook](xref:microsoft.quantum.install.jupyter) 進行整合。 使用內建的 API 來將您的程式與 [Python](xref:microsoft.quantum.install.python) 和 [.NET](xref:microsoft.quantum.install.cs) 主機語言配對。

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>嘗試量子運算和領域特有程式庫

撰寫並測試量子演算法，以探索疊加、糾纏和其他量子運算。 Q# 程式庫可讓您執行複雜的量子運算，而不必設計低層級的運算序列。

### <a name="run-programs-in-simulators"></a>在模擬器中執行程式

請在全狀態的量子模擬器 (範圍受限的 Toffoli 模擬器) 上執行您的量子程式，或在不同的資源估算器中測試您的 Q# 程式碼。 

## <a name="where-can-i-learn-more"></a>哪裡可以深入了解？

|||
| ---- | ---- |
| **我是量子運算的新手** | 檢閱[重要概念](xref:microsoft.quantum.overview.understanding)中的一些量子物理和量子運算基本知識。|
| **我想要深入了解 Q# 語言** | 在 [Q# 使用者指南](xref:microsoft.quantum.guide)中探索類型、運算式、變數和量子程式結構。|
| **我想要直接開始撰寫量子程式** | 在[快速入門](xref:microsoft.quantum.install)中設定您的 Q# 環境並開始撰寫量子程式。|

## <a name="how-does-q-work"></a>Q# 的運作方式為何？

Q# 程式可以編譯成獨立的命令列應用程式，或由以 Python 或 .NET 語言撰寫的主機程式加以呼叫。

當您編譯和執行程式時，程式會建立量子模擬器的執行個體，並於其中傳入 Q# 程式碼。 模擬器會使用 Q# 程式碼來建立量子位元(模擬量子粒子)，並套用轉換來修改其狀態。 然後，模擬器中的量子運算結果會傳回給程式。  

在模擬器中隔離 Q# 程式碼可確保演算法會遵循量子物理定律，並可在量子電腦上正確執行。

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>要如何使用 QDK？

為了撰寫和執行 Q# 程式所需的一切資源 (包括 Q# 編譯器、Q# 程式庫和量子模擬器) 都可以從本機電腦安裝及執行。 最終，您將能夠在實際的量子電腦上遠端執行 Q# 程式，但在這之前，QDK 所提供的量子模擬器會提供正確且可靠的結果。

- [從命令列執行 Q#](xref:microsoft.quantum.install.standalone) 是能夠最快開始使用的方式。

- [使用 IQ# 執行獨立的 Jupyter Notebook](xref:microsoft.quantum.install.jupyter)，IQ# 是用來編譯和模擬 Q# 程式並將其視覺化的 Jupyter 擴充功能。

- 如果您熟悉 [Python](xref:microsoft.quantum.install.python)，就可以用 Python 作為要開始使用的主機程式設計平台。 Python 不僅廣為開發人員使用，連科學家、研究人員和老師也都在使用。

- 如果您已有 [C#、F# 或 VB.NET](xref:microsoft.quantum.install.cs) 的經驗，而且熟悉 Visual Studio 開發環境，則您需要將幾個擴充功能新增至 Visual Studio 以使其做好準備而能用於 Q#。  

## <a name="summary"></a>摘要

Q# 是一種可用來開發量子程式的開放原始碼程式設計語言。 其具有可讓您建立複雜量子運算的程式庫，並有量子模擬器可供正確地執行和測試您的程式。 Q# 程式可作為獨立應用程式來執行，也可以從 Python 或 .NET 主機程式中加以呼叫，並可從您的本機電腦來撰寫、執行和測試。

## <a name="next-steps"></a>後續步驟

> [!div class="nextstepaction"]
> [量子運算的線性代數](xref:microsoft.quantum.overview.algebra)
