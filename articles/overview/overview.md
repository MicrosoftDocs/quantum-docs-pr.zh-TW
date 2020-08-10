---
title: 量子運算簡介
description: 了解量子運算是什麼、量子電腦的功用，以及如何學習量子運算。
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866973"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>簡介量子運算和 Quantum 開發套件

Microsoft Quantum 開發套件 (QDK) 是一組開放原始碼工具，專門設計來協助開發人員學習量子演算法和撰寫量子程式。 量子運算有望解決地球上的某些最大挑戰：在環境、農業、健康、能源、氣候、材料科學等領域，以及我們尚未遇過的其他問題。  

針對這些問題，即使是功能最強大的電腦也會遇到問題。 雖然量子技術才剛剛開始影響運算世界，但其影響深遠，可能會改變我們對運算的想法。

## <a name="what-is-quantum-computing"></a>什麼是量子運算？

量子一詞在現代用法中代表的是任何物理特性的最小可能離散單位，通常是指原子或次原子粒子的特性。 量子電腦會使用實際的量子粒子、人造原子或量子粒子的集體特性作為處理單位，算是大型、複數且昂貴的裝置。

利用量子物理的獨特行為，並將此行為運用到運算，量子電腦在傳統的程式設計方法中引進了新的概念，並且會善加利用疊加、糾纏和量子干涉等量子物理行為。

## <a name="what-can-a-quantum-computer-do"></a>量子電腦有何功用？

量子電腦並非可以更快完成所有運算的超級電腦，但量子電腦會在幾個領域有更加出色的表現。

- [量子模擬](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [碼編譯](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [搜尋](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [最佳化](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [機器學習服務](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>量子模擬

由於量子電腦會在運算中使用量子現象，因此很適合用來建立其他量子系統的模型。 光合作用、超導體和複雜分子的構造皆是量子程式所能模擬的量子力學範例。

## <a name="cryptography-and-shors-algorithm"></a>加密和秀爾演算法

西元 1994 年時，彼得‧秀爾展示了可擴縮的量子電腦，這種量子電腦可以破解廣泛使用的加密技術，例如 RSA 演算法。 傳統加密會仰賴不可駕馭的問題，例如整數分解或離散對數，但這些問題有許多都可以透過量子電腦更有效率地解決。

## <a name="search-and-grovers-algorithm"></a>搜尋和格羅弗演算法

西元 1996 年時，洛夫‧格羅弗開發了一種量子演算法，以大幅加快非結構化資料搜尋的解決方案，而能透過比任何傳統演算法更少的步驟來執行搜尋。

## <a name="quantum-inspired-computing-and-optimization"></a>受量子啟發的運算與最佳化

受量子啟發的演算法會使用量子原理來提升速度和正確性，但實作對象卻是傳統的電腦系統。 這種方法可讓開發人員立即運用新量子技術的威力，而不必等待仍屬新興產業的量子硬體。

最佳化是指在指定其所需結果和條件約束的情況下找出問題最佳解決方案的過程。 成本、品質或生產時間等都是產業界和科學界在做出重要決定時的關鍵因素。 在現今的傳統電腦上執行受量子啟發的最佳化演算法，便可找到截至目前為止還不可行的解決方案。 除了將交通流量最佳化以減少塞車情形，飛機閘門指派、包裹運送、工作排程等等也都能最佳化。 由於材料科學的突破，將會有新形式的能源、更大容量的電池、更輕更耐用的材料問市。

> [!NOTE]
> 請深入了解 Microsoft 受量子啟發的運算如何運用在[材料科學](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[風險管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)和[藥物](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)上。

## <a name="quantum-machine-learning"></a>量子機器學習

傳統電腦上的機器學習革新了科學界和企業界。 不過，由於將模型定型的運算成本高昂，因此會阻礙其發展和適用領域。 量子機器學習的領域會探索如何設計和實作量子軟體，以便讓機器學習的執行速度快過傳統電腦。

Quantum 開發套件隨附[量子機器學習程式庫](xref:microsoft.quantum.machine-learning.concepts.intro)，可讓您執行量子/傳統混合機器學習實驗。 此程式庫包含範例和教學課程，並且會提供必要工具供您實作新的量子和傳統混合演算法 (以電路為中心的量子分類器)，以解決受監督的分類問題。

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# 和 Microsoft Quantum 開發套件 (QDK)

Q# 是 Microsoft 的開放原始碼程式設計語言，可用來開發和執行量子演算法。 這是 [QDK](https://docs.microsoft.com/quantum/) (適用於 Q# 的完整功能開發套件) 的一部分，可與標準工具和語言搭配使用，以開發可在多種不同環境中執行的量子應用程式，包括內建的全狀態量子模擬器。

既有適用於 Visual Studio 和 VS Code 的擴充功能，也有可與 Python 和 Jupyter Notebook 搭配使用的套件。

QDK 包含標準程式庫，以及專門的化學、機器學習和數值程式庫。

文件中包含可讓您快速開始使用的 Q# 語言指南、教學課程和範例程式碼，並有內容豐富的文章可協助您深入了解量子運算的概念。  

## <a name="microsoft-quantum-hardware-partners"></a>Microsoft 量子硬體合作夥伴

Microsoft 與各家量子硬體公司合作，讓開發人員能夠透過雲端存取量子硬體。 利用 [Azure Quantum](https://azure.microsoft.com/services/quantum/) 平台和 Q# 語言，開發人員將能夠探索量子演算法，並在不同類型的量子硬體上執行其量子程式。

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) 和 [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) 都使用**以離子阱為基礎的**處理器，可利用電場中捕獲的個別離子，至於 [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) 則使用超導電路。

## <a name="next-steps"></a>後續步驟

[量子運算的重要概念](xref:microsoft.quantum.overview.understanding)
[快速入門](xref:microsoft.quantum.welcome)