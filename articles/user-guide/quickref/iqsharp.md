---
title: 我的 Q# 神奇命令
description: Q#Jupyter 筆記本的我魔術命令快速參考 Q# 頁面
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb7b5543ef9222e6bab2b1cbbc7e3ebb54863438
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867976"
---
# <a name="ino-locq-magic-commands"></a>我的 Q# 神奇命令

### <a name="general"></a>一般

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允許設定或查詢設定選項。
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目的電腦上執行指定的函式或作業。
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：傳回所有目前可用的魔術命令清單。
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供載入 NuGet 封裝的功能。
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：報告此核心的目前效能計量。
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目的電腦上執行指定的函式或作業。
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目的電腦上執行指定的函式或作業。
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 目前會話中可用的作業。
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供與目前工作區相關的動作。

### <a name="azure-quantum-integration"></a>Azure 量子整合

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：連接到 Azure 配量工作區，或顯示目前的線上狀態。
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure 量子工作區中執行作業。
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：顯示目前 Azure 量子工作區中的作業清單。
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：在目前的 Azure 量子工作區中顯示作業的結果。
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：顯示目前 Azure 配量工作區中作業的狀態。
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：將作業提交至 Azure 量子工作區。
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)：設定或顯示 Q# 在 Azure 量子工作區中提交作業的作用中執行目標。

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>來自 Microsoft. 量子化學套件的化學 () 

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題標記法。
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：將 fermion Hamiltonian 編碼為可使用的格式 Q# 。
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：將詞彙新增至 fermion Hamiltonian。
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：載入電子結構問題的 fermion Hamiltonian。 問題是從檔案載入，或做為引數傳遞。
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas 套件中的 Katas () 

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：執行單一測試，並報告測試是否成功傳遞。
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：檢查單一 kata 之測試的參考執行。
    具體來說，它會將單一工作的參考實替換成儲存格，並報告測試是否成功傳遞。
