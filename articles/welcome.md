---
uid: microsoft.quantum.welcome
title: 開始使用 Quantum Development Kit (QDK)
description: 了解如何使用 Microsoft Quantum Development Kit (QDK) 以 Q# 開始為量子專案進行程式設計。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907625"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>開始使用 Quantum Development Kit (QDK)

歡迎使用 Microsoft Quantum Development Kit！  
QDK 包含使用 Q# 建置自有量子程式和實驗所需的全部工具，而 Q# 是專為量子應用程式開發而設計的程式語言。 

若要直接開始，您可以前往 [QDK 安裝指南](xref:microsoft.quantum.install)。
接著，系統會引導您在 Windows、Linux 或 MacOS 機器上安裝 Quantum 開發套件，以便您撰寫自己的量子程式。

如果您不覺得已準備好開始撰寫程式碼，但想要深入了解量子運算和 Q#，我們鼓勵您繼續閱讀本文，以了解可以運用的資源。 在[關於量子運算的五個問題](#five-questions-about-quantum-computing)區段中，您可以找到清晰說明所尋求內容的連結！

## <a name="get-started-programming"></a>開始設計程式

Quantum 開發套件提供許多方式來了解如何使用 Q# 開發量子程式。
若要運用強大的量子功能，您可以試用我們的「快速入門」  ：

* [量子亂數產生器](xref:microsoft.quantum.quickstarts.qrng)是 "Q# Hello World" 樣式應用程式，可提供量子概念的簡介，還可讓您在幾分鐘內建置並執行量子應用程式。
* [搭配 Q# 使用的量子基本知識](xref:microsoft.quantum.write-program)會引導您撰寫 Q# 程式來示範一些關於量子程式設計的基本概念。 
    如果您尚未準備好開始撰寫程式碼，仍可在不安裝 QDK 的情況下繼續，同時大致了解 Q# 程式設計語言和量子運算的首要概念。
* [格羅弗搜尋演算法](xref:microsoft.quantum.quickstarts.search)會提供 Q# 的範例，摘要示範低階的量子操作，讓您了解 Q# 在表示量子演算法方面的能力。 
    本快速入門會引導您使用各種程式設計環境 (具有 Python 主機或 .NET 語言主機，以及具有 Visual Studio 或 Visual Studio Code) 來開發程式。

### <a name="learning-further"></a>進一步了解
* 如果您想要深入了解 Q# 程式設計，請參閱 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) - 這是一系列自學型程式設計練習，透過 Q# 程式設計練習向您介紹量子運算。
    其中有許多 Katas 也都是以 Q# Notebooks 的形式提供。 
* 我們的[範例存放庫](https://github.com/Microsoft/Quantum)會展示多個範例，說明如何使用 Q# 撰寫量子程式。 大部分的範例都是使用我們的開放原始碼[量子程式庫](https://github.com/Microsoft/QuantumLibraries)所撰寫，包括[標準](xref:microsoft.quantum.libraries.standard.intro)和[化學](xref:microsoft.quantum.chemistry.concepts.intro)程式庫 (下面提供詳細資訊)。

## <a name="five-questions-about-quantum-computing"></a>關於量子運算的五個問題

如果您是量子開發新手，我們知道這可能有點令人望而生畏。 我們提供了一些資源來協助您開始了解量子運算。 有了這些簡短文章的協助，我們相信您會急切想要立刻開始進行程式設計。
* [什麼是量子運算？](xref:microsoft.quantum.overview.what)
* [量子電腦有何功用？](xref:microsoft.quantum.overview.computers)
* [為什麼要學習量子運算？](xref:microsoft.quantum.overview.why)
* [什麼是 Q#？](xref:microsoft.quantum.overview.qsharp)
* [如何使用 Q# 學習量子運算？](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Quantum 開發套件文件

目前的文件包含下列其他主題。

### <a name="using-q"></a>使用 Q#
* [Quantum 開發技術](xref:microsoft.quantum.techniques.intro)指定以 Q# 建立量子程式的核心概念。 這些主題包括檔案結構、作業和函式、使用量子位元，以及一些進階主題。
* [Q# 語言參考](xref:microsoft.quantum.language.intro)詳細說明 Q# 語言，包括類型模型、運算式、陳述式和編譯器使用。
* [量子模擬器和主機應用程式](xref:microsoft.quantum.machines)說明如何執行量子演算法、可用的量子機器有哪些，以及如何為量子程式撰寫非 Q# 驅動程式。

### <a name="q-libraries"></a>Q# 程式庫
* [Q# 標準程式庫](xref:microsoft.quantum.libraries.standard.intro)說明可同時支援傳統語言控制需求與 Q# 量子演算法的作業和函式。 
    這些主題包括控制流程、資料結構、錯誤修正、測試和偵錯。 
* [Q# 化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)說明可支援量子化學模擬 (量子運算的重要應用程式) 的作業和函式。 這些主題包括模擬哈密頓力學和量子相位估算法等其他主題。
* [Q# 數值程式庫](xref:microsoft.quantum.numerics.intro)說明可支援以目標機器原生作業表示複雜算術函式的作業和函式。
* [Q# 程式庫參考](xref:microsoft.quantum.standardlibsintro)包含各命名空間的程式庫實體相關參考資訊。

### <a name="general-quantum-computing"></a>一般量子運算
* [量子運算概念](xref:microsoft.quantum.concepts.intro)包括線性代數與量子運算的相關性、量子位元的本質和使用、如何讀取量子電路等主題。
* [量子運算字彙](xref:microsoft.quantum.glossary)是有關量子運算和程式開發的一些重要用語的字彙。 
    如果您不熟悉此領域，這些字彙是您在閱讀我們的文件時的便利參考。
* [進一步閱讀](xref:microsoft.quantum.more-information)包含精選的參考，可供深入了解量子運算主題。

### <a name="additional-info"></a>其他資訊
* [Microsoft Quantum 開發套件版本資訊](xref:microsoft.quantum.relnotes)。


## <a name="be-a-part-of-the-q-open-source-community"></a>加入 Q# 開放原始碼社群
Quantum 開發套件是一種開放原始碼的開發套件，可使開發人員能夠讓所有人更容易存取量子運算，以便我們解決世界上最迫切的一些挑戰。  需要開放原始碼軟體的學術機構將能夠針對其量子學習和開發來部署 Q#。 開放原始碼的開發套件也讓開發人員和各領域專家有機會透過其程式碼來貢獻想法及促使改進。

您對於 Quantum 開發套件的意見反應、參與和貢獻都極為重要。  若要深入了解 Quantum 開發套件來源、提供意見反應，以及查明如何參與決策和對此不斷成長的量子開發平台做出貢獻，請參閱[對 Quantum 開發套件做出貢獻](xref:microsoft.quantum.contributing)。

如果您需要更多有關 Microsoft 量子運算計畫的一般資訊，請參閱 [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/)。
