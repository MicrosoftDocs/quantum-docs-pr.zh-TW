---
title: Quantum Development Kit 程式庫
description: 概述 Microsoft Quantum Development Kit 中包含的標準、化學和數值程式庫。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: d61fe459362fdb5f3550768a26b34656a8a538a7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869098"
---
# <a name="overview-of-no-locq-libraries"></a>Q# 程式庫概觀
Quantum Development Kit 提供了數個程式庫，讓您能夠更輕鬆地在 Q# 中開發量子應用程式。
在文件的這一節中，我們將說明這些程式庫，以及如何在您的程式中加以使用。

- [**標準程式庫**](xref:microsoft.quantum.libraries.standard.intro)：本節提供序言，定義 Q# 程式與目標電腦之間的介面，並且定義 Canon，這是一個 Q# 程式庫，可提供撰寫 Q# 程式時所使用的一般用途作業和函式。
- [**量子化學程式庫**](xref:microsoft.quantum.chemistry.concepts.intro)：本節說明量子化學程式庫，此程式庫可提供用來載入費米子 Hamiltonian 表示法的資料模型，以及處理這些標記法的量子模擬作業和函式。
- [**量子數值程式庫**](xref:microsoft.quantum.numerics.intro)：本節說明量子數值程式庫，此程式庫可提供數學函式主機的實作方式。 它支援整數 (帶正負號和不帶正負號) 和定點表示法。
- [**量子機器學習程式庫**](xref:microsoft.quantum.machine-learning.concepts.intro)：本節說明量子機器學習程式庫，其提供的連續分類器實作可利用量子計算來瞭解資料。

您可以從 GitHub 取得程式庫和程式碼範例的來源。
如需進一步資訊，請參閱[授權](xref:microsoft.quantum.libraries.licensing)。 請注意，套件參考 (「二進位檔」) 也適用於程式庫，並提供另一種在專案中包含程式庫的方式。
透過 [NuGet](https://nuget.org) 可以很方便地取得這些資源。
