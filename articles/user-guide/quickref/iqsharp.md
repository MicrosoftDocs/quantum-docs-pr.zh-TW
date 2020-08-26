---
title: 我的 Q# 神奇命令
description: Q#使用 Jupyter 筆記本的 I 魔術命令快速參考頁面 Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863688"
---
# <a name="ino-locq-magic-commands"></a>我的 Q# 神奇命令

### <a name="general"></a>一般

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允許設定或查詢設定選項。
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目的電腦上執行指定的函數或作業。
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：傳回所有目前可用魔術命令的清單。
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen)：列出目前開啟的命名空間及其別名。
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供載入 NuGet 套件的功能。
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：報告此核心目前的效能計量。
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project)：提供可查看或加入 Q# 專案參考的功能。 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目的電腦上執行指定的函數或作業。
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目的電腦上執行指定的函數或作業。
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 目前會話中的可用作業。
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供與目前工作區相關的動作。

### <a name="azure-quantum-integration"></a>Azure Quantum 整合

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：連接到 Azure Quantum 工作區，或顯示目前的連接狀態。
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure Quantum 工作區中執行工作。
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：顯示目前 Azure Quantum 工作區中的作業清單。
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：顯示目前 Azure Quantum 工作區中工作的結果。
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：顯示目前 Azure Quantum 工作區中工作的狀態。
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：將作業提交至 Azure Quantum 工作區。
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)：設定或顯示 Q# Azure Quantum 工作區中的作業提交使用中的執行目標。

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>來自 Microsoft 量子化學套件的化學 () 

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題表示。
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：將 fermion Hamiltonian 編碼為可使用的格式 Q# 。
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：將詞彙新增至 fermion Hamiltonian。
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：針對電子結構問題載入 fermion Hamiltonian。 問題是從檔案載入，或做為引數傳遞。
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (Katas 套件) 

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：執行單一測試，並報告測試是否成功傳遞。
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：檢查單一 kata 測試的參考執行。
    具體而言，它會將單一工作的參考實作為儲存格，並報告測試是否成功通過。
