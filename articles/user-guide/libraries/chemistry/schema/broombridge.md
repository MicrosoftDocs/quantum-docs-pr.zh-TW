---
title: Broombridge 量子化學架構
description: 概述 Broombridge 量子化學架構，用來建立 Microsoft 量子開發工具組的真實世界化學問題模型。
author: martinro
ms.author: martinro
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: e580fd8267cc7ba30533d557eceb486f8c205be6
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835769"
---
# <a name="broombridge-quantum-chemistry-schema"></a><span data-ttu-id="1b936-103">Broombridge 量子化學架構</span><span class="sxs-lookup"><span data-stu-id="1b936-103">Broombridge Quantum Chemistry Schema</span></span> # 

<span data-ttu-id="1b936-104">強大的計算化學軟體（例如 [NWChem](http://www.nwchem-sw.org/) ）可讓您建立各種實際化學問題的模型。</span><span class="sxs-lookup"><span data-stu-id="1b936-104">Powerful computational chemistry software such as [NWChem](http://www.nwchem-sw.org/) allows you to model a wide range of real-world chemistry problems.</span></span> <span data-ttu-id="1b936-105">為了使用 Microsoft 量子化學程式庫存取 NWChem 分子模型，您可以使用名為**Broombridge**的[YAML](https://en.wikipedia.org/wiki/YAML)架構架構。</span><span class="sxs-lookup"><span data-stu-id="1b936-105">In order to access NWChem molecular models with the Microsoft Quantum Chemistry library, you use a [YAML](https://en.wikipedia.org/wiki/YAML)-based schema named **Broombridge**.</span></span> <span data-ttu-id="1b936-106">在 [參考] 中， [選擇的名稱](https://en.wikipedia.org/wiki/Broom_Bridge) 會被歡度為 hamiltonian 的發源地。</span><span class="sxs-lookup"><span data-stu-id="1b936-106">The name was chosen in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) which in some circles is celebrated as a birthplace of Hamiltonians.</span></span> 

<span data-ttu-id="1b936-107">[NWChem](https://github.com/nwchemgit/nwchem) 是在「寬鬆教育團體授權」 (ECL) 2.0 授權所授權的開放原始碼專案。</span><span class="sxs-lookup"><span data-stu-id="1b936-107">[NWChem](https://github.com/nwchemgit/nwchem) is an Open Source project licensed under the permissive Educational Community License (ECL) 2.0 license.</span></span> <span data-ttu-id="1b936-108">[Broombridge 量子化學架構](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) 是一個開放原始碼架構，其中包含遵循[RFC 2119](https://tools.ietf.org/html/rfc2119)的[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)，以及在 MIT 授權下授權的[驗證程式腳本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。</span><span class="sxs-lookup"><span data-stu-id="1b936-108">The [Broombridge Quantum Chemistry Schema](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) is an Open Source schema that includes a [definition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) following [RFC 2119](https://tools.ietf.org/html/rfc2119) and a [validator script](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licensed under the MIT license.</span></span> 

<span data-ttu-id="1b936-109">以 YAML 為基礎的 Broombridge 是一種結構化、人類看得懂、可編輯的方式，代表電子結構問題。</span><span class="sxs-lookup"><span data-stu-id="1b936-109">Being YAML-based, Broombridge is a structured, human-readable and human-editable way of representing electronic structure problems.</span></span> <span data-ttu-id="1b936-110">尤其是可以表示下列資料：</span><span class="sxs-lookup"><span data-stu-id="1b936-110">In particular, the following data can be represented:</span></span>
- <span data-ttu-id="1b936-111">您可以使用一或兩個 electron 的積分來表示 Fermionic Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="1b936-111">Fermionic Hamiltonians can be represented using one- and two-electron integrals.</span></span>
- <span data-ttu-id="1b936-112">您可以使用建立順序來呈現地面和驚喜的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b936-112">Ground and excited states can be presented using creation sequences.</span></span>
- <span data-ttu-id="1b936-113">您可以指定能源等級的上限和下限。</span><span class="sxs-lookup"><span data-stu-id="1b936-113">Upper and lower bounds of energy levels can be specified.</span></span>

<span data-ttu-id="1b936-114">您可以使用各種方法從 NWChem 產生資料，例如使用 NWChem 的完整安裝來執行化學投影片 (例如，在執行) 時輸出 Broombridge 的 [NWChem 程式庫](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) 中所提供的專案，或 NWChem 的 docker 映射，也可以用來從化學投影片產生 Broombridge。</span><span class="sxs-lookup"><span data-stu-id="1b936-114">Data can be generated from NWChem using various methods, such as using a full installation of NWChem to run chemistry decks (for example the ones provided in the [NWChem library](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) that output Broombridge as part of the run), or a docker image of NWChem which can also be used to generate Broombridge from chemistry decks.</span></span> <span data-ttu-id="1b936-115">若要快速開始使用計算化學，而不需要安裝任何化學軟體，您可以使用視覺化介面 NWChem 由 [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號提供的介面。</span><span class="sxs-lookup"><span data-stu-id="1b936-115">To get started with computational chemistry quickly without having to install any chemistry software, you can use the visual interface to NWChem provided by [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span>

<span data-ttu-id="1b936-116">概括而言，NWChem 和 Microsoft 量子開發工具組之間的相互作用可哥視化如下： ![ 化學堆疊 ](~/media/broombridge.png) 藍色陰影方塊代表 Broombridge 架構，而各種灰色陰影方塊則代表其他內部資料標記法，這些標記法是根據實際化學問題，選擇用來代表和處理計算化學的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="1b936-116">At a high level, the interplay between NWChem and the Microsoft Quantum Development Kit can be visualized as follows: ![Chemistry stack](~/media/broombridge.png) The blue shaded box represents the Broombridge schema, the various grey shaded boxes represent other internal data representations that were chosen to represent and process quantum algorithms for computational chemistry based on real-world chemistry problems.</span></span>

<span data-ttu-id="1b936-117">量子開發工具組範例存放庫中的 [整數/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) 資料夾包含使用 Broombridge 架構定義的多個化學標記法。</span><span class="sxs-lookup"><span data-stu-id="1b936-117">The [Integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains multiple chemical representations defined using the Broombridge schema.</span></span>
