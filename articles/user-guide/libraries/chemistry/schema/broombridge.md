---
title: Broombridge 量子化學架構
description: Broombridge 量子化學架構的總覽，用來建立 Microsoft Quantum Development Kit 的實際化學問題模型。
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274647"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化學架構 # 

強大的計算化學軟體（例如[NWChem](http://www.nwchem-sw.org/) ）可讓您建立各種真實世界化學問題的模型。 若要使用 Microsoft 量子化學程式庫來存取 NWChem 分子模型，您可以使用名為**Broombridge**的[YAML](https://en.wikipedia.org/wiki/YAML)型架構。 已選擇名稱參考中的[地標](https://en.wikipedia.org/wiki/Broom_Bridge)，其中某些圓形的慶祝為 Hamiltonians 的 birthplace。 

[NWChem](https://github.com/nwchemgit/nwchem)是以「寬鬆教育機構授權（ECL）2.0 授權」授權的開放原始碼專案。 [Broombridge 量子化學架構](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)）是一個開放原始碼架構，其中包含下列[RFC 2119](https://tools.ietf.org/html/rfc2119)的[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)，以及在 MIT 授權下授權的[驗證程式腳本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。 

Broombridge 是以 YAML 為基礎，這是一種結構化、人類看得懂、人類可編輯的方法，代表電子結構的問題。 特別的是，可以表示下列資料：
- Fermionic Hamiltonians 可以使用一和二 electron 的積分來表示。
- 您可以使用建立順序來呈現地面和興奮狀態。
- 可以指定能源層級的上限和下限。

您可以使用各種方法從 NWChem 產生資料，例如使用 NWChem 的完整安裝來執行化學投影片（例如，在[NWChem 程式庫](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)中提供的範本，其會在執行時輸出 Broombridge），或 NWChem 的 docker 映射（也可用來從化學投影片產生 Broombridge）。 若要快速開始使用計算化學，而不需要安裝任何化學軟體，您可以使用視覺化介面來 NWChem [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號所提供的。

概括而言，NWChem 和 Microsoft Quantum Development Kit 之間的相互作用可以視覺化如下： ![ 化學 ](~/media/broombridge.png) 的堆疊藍色陰影方塊代表 Broombridge 架構，而各種灰色陰影框則代表其他內部資料標記法，這些代表已選擇用來表示和處理根據實際化學問題計算化學的量子演算法。

[量子開發工具組範例] 存放庫中的 [[整數/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) ] 資料夾包含使用 Broombridge 架構定義的多個化學標記法。
