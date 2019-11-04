---
title: Broombridge-量子化學架構
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185319"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化學架構 # 

強大的計算化學軟體（例如[NWChem](http://www.nwchem-sw.org/) ）可讓您建立各種真實世界化學問題的模型。 為了存取具有 Microsoft 量子化學程式庫的 NWChem 分子模型，我們使用以[YAML](https://en.wikipedia.org/wiki/YAML)為基礎的架構，我們稱之為**Broombridge**。 已選擇名稱參考中的[地標](https://en.wikipedia.org/wiki/Broom_Bridge)，其中某些圓形的慶祝為 Hamiltonians 的 birthplace。 

[NWChem](https://github.com/nwchemgit/nwchem)是以「寬鬆教育機構授權（ECL）2.0 授權」授權的開放原始碼專案。 Broombridge 是在[此](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)指定的開放原始碼架構，其隨附于[RFC 2119](https://tools.ietf.org/html/rfc2119)的[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)，以及在 MIT 授權下授權的[驗證程式腳本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。 

Broombridge 是以 YAML 為基礎，這是一種結構化、人類看得懂、人類可編輯的方法，代表電子結構的問題。 特別的是，可以表示下列資料： 
- Fermionic Hamiltonians 可以使用一和二 electron 的積分來表示。 
- 您可以使用建立順序來呈現地面和興奮狀態。
- 可以指定能源層級的上限和下限。

您可以輕鬆地從 NWChem 產生資料格式：有各種方法可供使用，範圍從完整安裝的 NWChem 到執行化學組（例如[這裡](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)提供的），以及透過 docker 執行的輸出 BroombridgeNWchem 的影像，也可以用來從化學牌組產生 Broombridge。 最後，若要快速開始使用計算化學，而不需要安裝任何化學軟體， [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號介面會提供給 NWChem。 

概括而言，NWChem 和 Microsoft Quantum Development Kit 之間的相互作用可以視覺化如下： ![化學堆疊](~/media/broombridge.png) 藍色陰影方塊代表 Broombridge 架構，各種灰色陰影框代表其他內部根據實際化學問題，選擇用來表示和處理計算化學之配量演算法的資料標記法。 

[這裡](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)提供使用 Broombridge 架構定義的多個化學標記法。

