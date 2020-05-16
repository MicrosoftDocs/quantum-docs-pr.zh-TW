---
title: 'IQ # 魔術命令'
description: '使用 Q # Jupyter 筆記本的 IQ # 魔術命令快速參考頁面'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431014"
---
# <a name="iq-magic-commands"></a>IQ # 魔術命令

### <a name="general"></a>一般

- `%config`：設定或取得設定喜好設定。
- `%estimate`：在 QuantumSimulator 目的電腦上執行指定的函式或作業。
- `%lsmagic`：傳回所有目前可用的魔術命令清單。
- `%package`：提供載入 Nuget 封裝的功能。
- `%performance`：報告此核心的目前效能計量。
- `%simulate`：在 QuantumSimulator 目的電腦上執行指定的函式或作業。
- `%toffoli`：在 ToffoliSimulator 模擬器目的電腦上執行指定的函式或作業。
- `%who`：提供與目前工作區相關的動作。
- `%workspace`：傳回目前會話中定義的所有作業和函式清單，不論是以互動方式或從目前工作區載入。

### <a name="chemistry"></a>化學

- `%chemistry.broombridge`：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題標記法。
- `%chemistry.encode`：將 fermion Hamiltonian 編碼成 Q # 可使用的格式。
- `%chemistry.fh.add_terms`：將詞彙新增至 fermion Hamiltonian。
- `%chemistry.fh.load`：載入電子結構問題的 fermion Hamiltonian。 問題是從檔案載入，或做為引數傳遞。
- `%chemistry.inputstate.load`：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。

### <a name="from-microsoftquantumkatas-package"></a>Katas 套件中的

- `%kata`：執行單一測試，並報告測試是否成功傳遞。
- `%check_kata`：檢查單一 kata 之測試的參考執行。
    具體來說，它會將單一工作的參考實替換成儲存格，並報告測試是否成功傳遞。
