---
title: Broombridge 量子化學架構
description: 概述 Broombridge 量子化學架構，用來建立 Microsoft 量子開發工具組的真實世界化學問題模型。
author: martinro
ms.author: martinro
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: e83d2d52fcdb2a30179ca6994d2c90f41cef7dbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856202"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化學架構 # 

強大的計算化學軟體（例如 [NWChem](http://www.nwchem-sw.org/) ）可讓您建立各種實際化學問題的模型。 為了使用 Microsoft 量子化學程式庫存取 NWChem 分子模型，您可以使用名為 **Broombridge** 的 [YAML](https://en.wikipedia.org/wiki/YAML)架構架構。 在 [參考] 中， [選擇的名稱](https://en.wikipedia.org/wiki/Broom_Bridge) 會被歡度為 hamiltonian 的發源地。 

[NWChem](https://github.com/nwchemgit/nwchem) 是在「寬鬆教育團體授權」 (ECL) 2.0 授權所授權的開放原始碼專案。 [Broombridge 量子化學架構](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) 是一個開放原始碼架構，其中包含遵循[RFC 2119](https://tools.ietf.org/html/rfc2119)的[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)，以及在 MIT 授權下授權的[驗證程式腳本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。 

以 YAML 為基礎的 Broombridge 是一種結構化、人類看得懂、可編輯的方式，代表電子結構問題。 尤其是可以表示下列資料：
- 您可以使用一或兩個 electron 的積分來表示 Fermionic Hamiltonian。
- 您可以使用建立順序來呈現地面和驚喜的狀態。
- 您可以指定能源等級的上限和下限。

您可以使用各種方法從 NWChem 產生資料，例如使用 NWChem 的完整安裝來執行化學投影片 (例如，在執行) 時輸出 Broombridge 的 [NWChem 程式庫](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) 中所提供的專案，或 NWChem 的 docker 映射，也可以用來從化學投影片產生 Broombridge。 若要快速開始使用計算化學，而不需要安裝任何化學軟體，您可以使用視覺化介面 NWChem 由 [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號提供的介面。

概括而言，NWChem 和 Microsoft 量子開發工具組之間的相互作用可哥視化如下： ![ 化學堆疊 ](~/media/broombridge.png) 藍色陰影方塊代表 Broombridge 架構，而各種灰色陰影方塊則代表其他內部資料標記法，這些標記法是根據實際化學問題，選擇用來代表和處理計算化學的量子演算法。

量子開發工具組範例存放庫中的 [整數/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) 資料夾包含使用 Broombridge 架構定義的多個化學標記法。
