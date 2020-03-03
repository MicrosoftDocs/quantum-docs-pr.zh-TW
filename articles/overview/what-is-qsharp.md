---
title: Q# 和 QDK 是什麼？
description: 了解 Q#，其既是由 Microsoft 所建立來開發量子電腦應用程式的程式設計語言，也是 Microsoft Quantum Development Kit 的重要元件
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906996"
---
# <a name="what-are-q-and-the-qdk"></a>Q# 和 QDK 是什麼？

Q# 是一種程式設計語言，其具有專門設計的功能，可與量子運算搭配使用。
其作為 Microsoft Quantum Development Kit (QDK) 的重要元件，可為量子程式設計人員提供一個架構，讓您能夠專注於處理演算法，而不必擔心量子電腦的閘道序列最佳化或實體實作等技術細節。

QDK 包含各式各樣的工具，可為開發人員提供一切所需，讓其能夠開始撰寫量子程式。
除了 Q# 語言，QDK 還包含：
* 「Q# 程式庫」  ，可讓開發人員立即做好準備，開始建立真實的量子應用程式
* 可供執行 Q# 程式的各種「目標機器」  。 這些機器包括適用於較大型量子程式的資源估算器和模擬器，以及行為如同無雜訊量子電腦的全狀態量子模擬器。 後者非常適合用來完善概念、針對程式進行偵錯，以及了解量子物理，但若要有效率，就必須用在量子位元相對較少的程式上。 我們非常期待未來有一天能讓量子運算硬體成為目標機器。
* 可讓使用 Q# 變得盡可能順暢的「工具」  ，例如適用於 Visual Studio 和 VS Code 的擴充功能，以及可供與 Python 和 Jupyter Notebook 搭配使用的套件。
* 用來讓 Q# 與傳統主機語言 (例如 Python 和 C#) 配對的「API 文件」 

以 Microsoft Quantum Development Kit 開發的應用程式一般會包含兩個部分：
1. 一或多個量子演算法，使用 Q# 量子程式設計語言所實作，並由傳統主機程式來叫用。 這些演算法會由下列項目組成： 
    - Q# 運算：含有量子運算的副程式，以及 
    - Q# 函式：在量子演算法內使用的傳統副程式。
2. 一個傳統程式，以傳統的程式設計語言 (例如 Python 或 C#) 來實作，既作為主要進入點，又會在想要執行量子演算法時叫用 Q# 運算。

## <a name="write-quantum-programs-not-quantum-circuits"></a>撰寫量子程式而非量子電路

在量子運算初期，演算法是用類似古典運算中的電路圖來做出圖表化的視覺呈現。
雖然電路模型長年來在量子運算研究領域發揮了良好成效，但 Microsoft 相信開發人員可以超越量子電路，而使用 Q# 來開發量子演算法和應用程式。
建置 Q# 語言的目的，是要利用我們數十年來進行傳統軟體開發所獲得的成果，讓開發人員能夠使用針對量子運算而設計的高階語言功能。

## <a name="how-does-q-work"></a>Q# 的運作方式為何？

Q# 程式設計語言提供了一組直覺式的類型、作業和邏輯運算式來開發演算法，而您不需要顧慮量子電腦的內部邏輯。

Q# 的其中一個基本構成要素是 `Qubit` 類型，它無法複製或直接存取，就像實際的量子位元一樣。
不過，我們可加以測量，並將測量的結果儲存在 `Result` 變數中，這是可接受兩個可能值的 Q# 類型：`Zero` 和 `One`。
這樣的結構可確保演算法一律會遵循量子物理的法則，並且可在量子電腦或模擬器上正確執行。

Q# 也包含傳統邏輯功能 (例如條件和迴圈)，並且藉由細微的差異確保能遵循所有量子規則。
例如，限制執行迴圈的方式，確保不會在只能包含確定性傳統子程式的函式中呼叫量子作業。

Q# 程式通常會與以 C# 或 Python 撰寫的主機程式配對，這有助於組織傳統和量子程式碼。
除了支援 C# 和 Python 等語言以外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。

## <a name="what-can-i-use-q-for"></a>Q# 有哪些用途？

### <a name="use-q-to-learn-quantum-computing"></a>使用 Q# 學習量子運算

目前，若要學習量子運算，您必須學習電路模型，以定序的量子閘道和測量的形式了解演算法。 透過 Q# 您將可採用另一個途徑：藉由撰寫量子程式來學習量子運算。

### <a name="use-q-to-design-quantum-algorithms"></a>使用 Q# 設計量子演算法

Q# 可為您提供更多程式庫和使用者定義類型，以協助您實作工具來建置進階量子演算法。 例如，假設您需要讓兩個量子位元 q1 和 q2 相互糾纏。 您可以使用既有的內建作業 `PrepareEntangledState([q1], [q2])` 讓量子位元相互糾纏，而無須個別套用必要的閘道。

### <a name="use-q-to-estimate-quantum-resources"></a>使用 Q# 來估計量子資源

您可以使用 Quantum Development Kit (QDK) 提供的全態量子模擬器，模擬您的 Q# 程式執行。  QDK 也提供資源估算器，讓您解析 Q # 程式效能，看出在模擬器上執行會太大的程式。  這對演算法設計人員來說非常重要，因為他們可以微調程式使其使用較少的資源 (例如，較少量子位元執行較少作業)，以利盡早在較小規模的量子硬體上執行。

### <a name="use-q-to-validate-hardware-performance"></a>使用 Q# 來驗證硬體效能

Q# 的優點是可以只撰寫程式一次，就在量子模擬器上執行並偵錯，並在不同量子電腦硬體上執行。  您可以執行以 Q# 撰寫的基準測試程式來驗證硬體效能並比較結果，促成量子電腦的演進，和新量子電腦的問市。  

## <a name="next-steps"></a>後續步驟

* [要如何學習量子運算？](xref:microsoft.quantum.overview.learn)
* [開始使用 Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
