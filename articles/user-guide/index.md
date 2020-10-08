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
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771375"
---
# <a name="the-no-locq-user-guide"></a>Q# 使用者指南

歡迎使用 Q# 使用者指南！ 

在本指南提供的不同主題中，會詳細說明 Q# 語言的核心概念，以及撰寫量子程式所需的所有資訊。

## <a name="user-guide-contents"></a>使用者指南內容

- [Q# 基本概念](xref:microsoft.quantum.guide.basics)：Q# 程式設計語言的用途和功能概述。 

- [執行 Q# 程式](xref:microsoft.quantum.guide.host-programs)的方式：說明如何執行 Q# 程式，並概述您可以呼叫程式的各種方法：從命令列、從 Q# Jupyter Notebook、或從以 Python 或 .NET 語言撰寫的傳統主機程式。

### <a name="no-locq-language"></a>Q# 語言

- [Q#](xref:microsoft.quantum.guide.types)中的類型：配置 Q# 類型模型，並描述用於指定和使用類型的語法。

- [類型運算式](xref:microsoft.quantum.guide.expressions)：詳細說明如何指定、參考、結合和操作 Q# 中每個類型的值。 

### <a name="using-no-locq"></a>使用 Q#

- [Q#檔案結構](xref:microsoft.quantum.guide.filestructure)：描述 `*.qs` Q# 檔案的結構和語法。

- [作業和函式](xref:microsoft.quantum.guide.operationsfunctions)：詳細說明 Q# 語言的兩種可呼叫類型：「作業」包含量子位元暫存器上的動作，「函式」則嚴格地處理傳統資訊。 
    在這裡，您會了解如何定義和呼叫這些類型，包括伴隨 (adjoint) 和受控的量子作業版本。

- [變數](xref:microsoft.quantum.guide.variables)：描述 Q# 程式中變數的角色，以及如何有效地運用。 
    例如，您可以找到繫結範圍的相關資訊，以及不可變和可變變數之間的差異，以及如何指派或重新指派這些變數。

- [使用量子位元](xref:microsoft.quantum.guide.qubits)：說明用於處理個別量子和量子系統的 Q# 功能，尤其是對其執行分配、操作和測量的功能。 

- [控制流程](xref:microsoft.quantum.guide.controlflow)：詳細說明 Q# 中可用的程式設計控制流程模式，其中包括許多標準技術 (例如，條件式流程、for 迴圈、while 迴圈)，以及量子特有的「重複直到成功 (Repeat-Until-Success)」模式。

- [測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)：詳細說明一些技術，用來確保您的程式碼會執行其作業。 
    由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。 
    幸運的是，Q# 支援許多設計人員熟悉的傳統偵錯技術，以及屬於量子特有的偵錯技術。 其中包括在 Q# 中建立和執行單元測試、在程式碼中的值和機率內嵌*判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。 
    後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，[不複製定理](xref:microsoft.quantum.concepts.pauli))，以偵測計算的特定部分。

### <a name="quantum-simulators-and-resource-estimators"></a>量子模擬器和資源估算器

- [量子模擬器和主應用程式](xref:microsoft.quantum.machines)：概述可用的各種模擬器，以及主程式與目標機器如何共同運作，以執行 Q# 程式。

- [完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)：模擬完整量子狀態的目標機器。 適用於完整執行或偵錯規模較小的程式 (少於數十個量子位元)

- [資源估算器](xref:microsoft.quantum.machines.resources-estimator)：估算在量子電腦上執行 Q# 作業指定執行個體所需的資源。

- [追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：執行量子程式，而不實際模擬量子電腦的狀態，因此可以執行使用數千個量子位元的量子程式。 適用於在量子程式內進行傳統程式碼的偵錯，以及預估所需的資源。

- [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)：特殊用途的量子模擬器，可對數百萬個量子位元使用，但僅適用於具有一組有限量子作業 (X、CNOT 和多重受控 X) 的程式。

### <a name="quick-reference-pages"></a>快速參考指南

- [IQ#Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter Notebook 中的 IQ# 魔術命令快速參考頁面。
