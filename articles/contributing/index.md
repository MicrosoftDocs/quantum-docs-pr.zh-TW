---
title: 參與 Microsoft Quantum Development Kit
description: 了解如何參與 Microsoft Quantum Development Kit 和量子開發社群。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 63c6f90a511c7bd14435b2e593af0d8615c18519
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904871"
---
# <a name="contributing-to-the-quantum-development-kit"></a>參與 Quantum Development Kit #

Quantum Development Kit 不僅僅是用來編寫量子程式的工具集合。
它還是廣大社群的一部分，此社群裡面的人從事的是探索量子運算、執行量子演算法的研究、為量子裝置開發新的應用程式，以及致力於充分運用量子程式設計。
作為該社群的一員，Quantum Development Kit 的目標是要為各種背景的量子開發人員提供其所需的功能。
您對 Quantum Development Kit 的參與，將會因為改善其他量子開發人員所使用的工具、這些工具的記載方式、甚至是因為建立新的特性和功能來協助讓整個量子程式設計社群成為探索和創作的沃土，而實現此一目標。
對於您的參與，以及有機會與您合作讓我們的社群成為最優秀的基地，我們非常感激。

在本指南中，我們會提供一些建議，讓您了解如何讓您的參與盡可能地對更廣泛的量子程式設計社群產生作用。

## <a name="building-community"></a>建立社群 ##

若想要參與，首先永遠是把您要參與的社群放在心上。
只有對量子程式設計社群中的同好和其他人士保持敬意和專業態度，才能確保您投入的心力能夠建立最佳且最受歡迎的社群。

有鑑於此，所有 Quantum Development Kit 專案都已採用 [Microsoft 開放原始碼管理辦法](https://opensource.microsoft.com/codeofconduct/)。
如需詳細資訊，請參閱[管理辦法常見問題集](https://opensource.microsoft.com/codeofconduct/faq/)，如有任何其他問題或意見，則請連絡 [opencode@microsoft.com](mailto:opencode@microsoft.com)。

## <a name="what-kinds-of-contributions-help-the-community"></a>哪種參與有助於社群？ ##

有許多不同的方式可透過您的參與來協助量子程式設計社群。
在本指南中，我們將著重在三種與 Quantum Development Kit 特別相關的方式。
這些方法全都是建立量子社群來支援社群成員的關鍵。
話雖如此，但這份清單絕對不夠詳盡，因此我們鼓勵您探索其他方法，在量子程式設計的保證下協助建立社群！

- **報告錯誤。** 修正錯誤和其他類型問題的第一個步驟就是要先發現。 如果您在 Quantum Development Kit 中發現錯誤，讓我們知道便能協助我們修正錯誤，並為量子程式設計社群製作一組更好的工具。
- **改善文件。** 任何文件集永遠都有變得更好的餘地、可以涵蓋更多細節，可以更容易看懂。
- **參與程式碼。** 毫無疑問，最直接的參與方式就是在 Quantum Development Kit 中新增程式碼。

這些不同種類的參與全都十分寶貴，我們為此深表感謝。
在本指南的其餘部分，我們將提供有關如何做出每一種參與的建議。

## <a name="where-do-contributions-go"></a>參與會進到何處？ ##

Quantum Development Kit 包含許多不同的部分，在這些部分合作之下，才得以實現用來編寫量子程式的平台。
這些不同的部分各自都會在不同的存放庫找到其歸屬，因此，較早事物的分類方式便是每個參與最適合的歸屬。

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum)：內有範例和工具可協助您開始使用 Quantum Development Kit。
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries)：適用於 Quantum Development Kit 的標準和領域專屬程式庫。
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)：自學型程式設計練習，可供學習量子運算和 Q# 程式設計語言。
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler)：Q# 編譯器、Visual Studio 擴充功能和 Visual Studio Code 擴充功能。
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime)：適用於 Quantum Development Kit 的模擬架構、程式碼產生和模擬目標電腦。
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp)：適用於 Q# Jupyter 核心和 Python 主機功能，以及可供在雲端環境中使用 IQ# 的 Docker 映像。
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr)： https://docs.microsoft.com/quantum 所發佈文件的原始程式碼。

> [!NOTE]
> 很遺憾地，我們目前無法接受 [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) 存放庫上的程式碼和文件參與，但我們還是非常感謝您提出錯誤報告。

另外還有一些更特殊化的存放庫，著重在不同的事件或與 Quantum Development Kit 相關的輔助功能。

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty)：適用於 Q# 語法的 LaTeX 格式化支援。
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019)：適用於 Deutsch–Jozsa 教學課程的 IQ# Notebook，此教學課程是在 2019 年的實習研討會中提供的。

## <a name="next-steps"></a>後續步驟 ##

感謝您成為 Quantum Development Kit 社群的一部分，很高興您能做出參與！
如果您想要深入了解如何參與，請繼續閱讀下列指南。

> [!div class="nextstepaction"]
> [了解如何報告錯誤](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [了解如何參與文件](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [了解如何開啟提取要求](xref:microsoft.quantum.contributing.pulls)
