---
title: Q# 使用者指南
description: 使用者指南的用途和內容概觀
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231752"
---
# <a name="the-no-locq-user-guide"></a>Q# 使用者指南

歡迎使用 Q# 使用者指南！ 

在本指南的不同主題中，我們將介紹使用 Q# 開發量子程式的一些基本概念。

如需 Q# 量子程式設計語言的完整規格和檔，請參閱 [Q# 語言指南](xref:microsoft.quantum.qsharp.index)。 

## <a name="user-guide-contents"></a>使用者指南內容

- [Q#程式](xref:microsoft.quantum.guide.programs)：Q# 中的量子程式快速簡介。 

- [執行 Q# 程式](xref:microsoft.quantum.guide.host-programs)的方式：說明如何執行 Q# 程式，並概述您可以呼叫程式的各種方法：從命令列、從 Q# Jupyter Notebook、或從以 Python 或 .NET 語言撰寫的傳統主機程式。

- [測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)：詳細說明一些技術，用來確保您的程式碼會執行其作業。 
    由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。 
    幸運的是，Q# 支援許多設計人員熟悉的傳統偵錯技術，以及屬於量子特有的偵錯技術。 其中包括在 Q# 中建立和執行單元測試、在程式碼中的值和機率內嵌 *判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。 
    後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，[不複製定理](xref:microsoft.quantum.concepts.pauli))，以偵測計算的特定部分。

### <a name="quantum-simulators-and-resource-estimators"></a>量子模擬器和資源估算器

- [量子模擬器和主應用程式](xref:microsoft.quantum.machines)：概述可用的各種模擬器，以及主程式與目標機器如何共同運作，以執行 Q# 程式。

- [完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)：模擬完整量子狀態的目標機器。 適用於完整執行或偵錯規模較小的程式 (少於數十個量子位元)

- [資源估算器](xref:microsoft.quantum.machines.resources-estimator)：估算在量子電腦上執行 Q# 作業指定執行個體所需的資源。

- [追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：執行量子程式，而不實際模擬量子電腦的狀態，因此可以執行使用數千個量子位元的量子程式。 適用於在量子程式內進行傳統程式碼的偵錯，以及預估所需的資源。

- [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)：特殊用途的量子模擬器，可對數百萬個量子位元使用，但僅適用於具有一組有限量子作業 (X、CNOT 和多重受控 X) 的程式。

### <a name="quick-reference-pages"></a>快速參考指南

- [IQ#Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter Notebook 中的 IQ# 魔術命令快速參考頁面。
