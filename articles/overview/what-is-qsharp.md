---
title: 什麼是 Q#？
description: 了解 Microsoft 為了開發量子電腦的應用程式而建立的程式設計語言 Q#
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04d72bafe390ff5c79af408db1d9400754b06ce
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864282"
---
# <a name="what-is-q"></a>什麼是 Q#？

Q# 是一種程式設計語言，具備量子運算方面的特殊功能。

Q# 可為量子程式設計人員提供一個架構，讓您能夠專注於演算法，而無須分神考量閘道序列最佳化或量子電腦的實體執行等技術細節。

Q# 程式設計語言提供了一組直覺式的類型、作業和邏輯運算式來開發演算法，而您不需要顧慮量子電腦的內部邏輯。

## <a name="code-algorithms"></a>程式碼演算法

在量子運算初期，演算法是用類似古典運算中的電路圖來做出圖表化的視覺呈現。  雖然電路模型長年來在量子運算研究領域發揮了良好成效，但 Microsoft 相信開發人員可以超越量子電路，而使用 Q# 來開發量子演算法和應用程式。 建置 Q# 語言的目的，是要利用我們數十年來進行傳統軟體開發所獲得的成果，讓開發人員能夠使用針對量子運算而設計的高階語言功能。

## <a name="how-does-q-work"></a>Q# 的運作方式為何？

Q# 的其中一個基本構成要素是 `Qubit` 類型，它無法複製或直接存取，就像實際的量子位元一樣。 不過，我們可加以測量，並將測量的結果儲存在 `Result` 變數中，這是可接受兩個可能值的 Q# 類型：`Zero` 和 `One`。 這樣的結構可確保演算法一律會遵循量子物理的法則，並且可在量子電腦或模擬器上正確執行。

Q# 也包含傳統邏輯功能 (例如條件和迴圈)，並且藉由細微的差異確保能遵循所有量子規則。 例如，限制執行迴圈的方式，確保不會在只能包含確定性傳統子程式的函式中呼叫量子作業。

Q# 程式通常會與以 C# 或 Python 撰寫的主機程式配對，這有助於組織傳統和量子程式碼。 除了支援 C# 和 Python 等語言以外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。

## <a name="use-q-to-learn-quantum-computing"></a>使用 Q# 學習量子運算

目前，若要學習量子運算，您必須學習電路模型，以定序的量子閘道和測量的形式了解演算法。 透過 Q# 您將可採用另一個途徑：藉由撰寫量子程式來學習量子運算。

## <a name="use-q-to-design-quantum-algorithms"></a>使用 Q# 設計量子演算法

Q# 可為您提供更多程式庫和使用者定義類型，以協助您實作工具來建置進階量子演算法。 例如，假設您需要讓兩個量子位元 q1 和 q2 相互糾纏。 您可以使用既有的內建作業 `PrepareEntangledState([q1], [q2])` 讓量子位元相互糾纏，而無須個別套用必要的閘道。

## <a name="use-q-to-estimate-quantum-resources"></a>使用 Q# 來估計量子資源

您可以使用 Quantum Development Kit (QDK) 提供的全態量子模擬器，模擬您的 Q# 程式執行。  QDK 也提供資源估算器，讓您解析 Q # 程式效能，看出在模擬器上執行會太大的程式。  這對演算法設計人員來說非常重要，因為他們可以微調程式使其使用較少的資源 (例如，較少量子位元執行較少作業)，以利盡早在較小規模的量子硬體上執行。

## <a name="use-q-to-validate-hardware-performance"></a>使用 Q# 來驗證硬體效能

Q# 的優點是可以只撰寫程式一次，就在量子模擬器上執行並偵錯，並在不同量子電腦硬體上執行。  您可以執行以 Q# 撰寫的基準測試程式來驗證硬體效能並比較結果，促成量子電腦的演進，和新量子電腦的問市。  

## <a name="next-steps"></a>後續步驟

* [如何學習量子運算？](xref:microsoft.quantum.overview.learn)
* [開始使用 Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
