---
title: 如何使用 Q# 學習量子運算？
description: 可供獲得基本數理知識的資源，以協助您開始使用量子運算。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 17fc4e7a73f93a86d981996bf8b59309bccb6e67
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907744"
---
# <a name="how-to-learn-about-quantum-computing"></a>如何學習量子運算？

取得指引以學習量子運算並編寫第一個程式。 本指南並不詳盡，僅供作為入門之用。

## <a name="getting-started-overview"></a>使用者入門概觀

[開始使用 Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) 提供使用 Q# 進行量子運算的高階概觀，包括撰寫第一個 Q# 程式的教學課程、快速入門指南，以及適於開發量子程式的 Q# 量子程式庫簡介。

## <a name="learning-the-basics-what-do-you-need-to-know"></a>學習基本概念：您需要知道什麼？

您不需要知道量子物理就能學習 Q# 和量子運算，也可以開始編寫量子應用程式。

這些概念可讓您深入了解所需的基本知識，以便您可以開始編寫量子程式。  

* [基本的量子力學](xref:microsoft.quantum.concepts.intro)：我們說過，就算不知道量子物理也能開始編碼 (實際上也確實如此！)。 但如果對量子力學和其數學符號有一些基本概念，將有助於您了解量子程式設計。

* **線性代數 (向量和矩陣)** ：在量子運算中，量子態會以向量表示，並以線性轉換的方式對這些向量實施量子操作。  這裡有[有關線性代數的 Jupyter Notebook 教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)。  您也可以在我們的[向量和矩陣](xref:microsoft.quantum.concepts.vectors)相關概念指南中，閱讀有關線性代數的詳細資訊。

* **複雜算術**：量子態向量的係數為複數。 即使不懂複數，您也可以了解一些基本的量子運算概念，但若要更深入地運用，您就必須在量子工具組中納入複數。  這裡有[有關複雜算術的 Jupyter Notebook 教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)，其中說明處理量子運算所需的一些數學背景。 

現在您已具備基本概念，可以開始學習撰寫量子程式。  有幾個不同的做法：

## <a name="do-the-quantum-katas"></a>使用 Quantum Katas

[Quantum Katas](xref:microsoft.quantum.overview.katas) 是我們一系列開放原始碼形式的自學型教學課程，目標是要同時讓您學會量子運算和 Q# 程式設計的要素。  每個 Kata 都會參考其他學習材料，您可以用來學習成功完成 Katas 所需的量子運算概念。  

## <a name="dive-into-the-theory"></a>深入了解理論

您可能會想要深入了解量子力學和量子運算的理論。 這裡有一份實用資料的清單：

* 從我們的[量子運算概念](xref:microsoft.quantum.concepts.intro)指南來開始，裡面彙編了量子運算的基本概念。
* 「使用 Python 和 Q# 學習量子運算」  (Sarah C. Kaiser 和 Christopher E. Granade) 為幾乎不懂量子力學、但有一些程式設計背景的人提供了出色的簡介。
* 「量子運算和量子資訊」  (Michael A. Nielsen, Isaac L. Chuang) 是量子運算領域中最常被引用的教科書，且被視為這方面主題的標準教科書。 本書假設讀者先前只懂一點量子力學和電腦科學。 對於想要對此主題有嚴謹認識的讀者，以及正在尋找參考資料以獲得進階概念的讀者來說，本書是很好的選擇。
* MIT OpenCourseWare 有優秀的[線上課程](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr)，授課者是 Allan Adams，您可從中學到量子力學的基礎知識。 適合想要進一步了解基礎物理學的開發人員。

## <a name="join-the-quantum-community"></a>加入量子社群

您不必獨自學習，有一大群愛好者和專家會樂意幫忙。 不要害怕提出問題！

* 如果您有任何關於 Q# 或量子運算的問題，請不要遲疑，立即探訪量子運算 StackExchange 網站。 如果在其中找不到您的具體問題，請隨時發問。 
* 造訪 [Q# 部落格](https://devblogs.microsoft.com/qsharp/)和 [Microsoft Quantum 部落格](https://cloudblogs.microsoft.com/quantum/)，隨時了解有關 Q# 的最新消息和資源。
* 造訪 [Q# 社群](https://qsharp.community/)和 [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp)，以尋找更多資源和資料。

 如果您想要教授關於量子運算的課程，[Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) 可以協助提供課程協助。  

