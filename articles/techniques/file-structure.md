---
title: 量子開發技術簡介 |Microsoft Docs
description: 量子開發技術簡介
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442561"
---
# <a name="q-program-overview"></a>Q# 程式概觀

問 # 是一種可調整、多架構的領域專屬程式設計語言，適用于量子運算。 問 # 是一種量副程式設計語言，它可以用來描述如何在量子機器上執行指令。 可設為目標的電腦範圍從模擬器到實際的量子硬體。 問 # 是可擴充的：它可以用來撰寫簡單的示範程式，像是在幾個 qubits 上執行的「傳送」，但也支援撰寫大型、複雜的程式，例如模擬複雜的分子驅使分子，這會需要含有數百萬 qubits 的大型機器。 雖然大型實體機器仍在未來，但問 # 可讓程式設計人員立即設計複雜的量子演算法。 什麼是更多，Q # 支援以可擴充的方式進行各種工作，例如，偵錯工具、分析、資源估計和特定特殊用途的模擬。 

從技術觀點來看，配量程式可視為一組特定的傳統函式，當呼叫這些函式時，會產生量子線路作為其副作用。 該觀點的重要結果是，以 Q # 撰寫的程式並不會直接 qubits 本身的模型，而是說明傳統的控制項電腦與這些 qubits 的互動方式。
根據設計，Q # 因此不會直接定義配量狀態或其他量子機制的屬性，而是間接透過語言中所定義之各種副程式的動作來進行。
例如，請考慮 >量子計算概念指南》中所討論的狀態 $ \ket{+} = \left （\ket{0} + \ket{1}\right）/\sqrt{2}$。[](xref:microsoft.quantum.concepts.intro)
若要在 Q # 中準備此狀態，我們會使用 qubits 在 $ \ket{0}$ state 中初始化的事實，以及 $ \ket{+} = H\ket{0}$，其中 $H $ 是 Hadamard 轉換：

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Tranformations 量子狀態的 Q #

重要的是，在撰寫上述程式時，我們並未明確參考 Q # 內的狀態，而是說明我們的程式如何*轉換*狀態。
因此，類似于圖形著色器程式如何為每個頂點累積轉換的描述，Q # 中的量副程式會累積轉換成配量狀態。
這可讓我們完全無從得知每個目的電腦上的量子狀態為何，這*可能會有*不同的解讀，視電腦而定。 

從 Q # 程式的角度來看，qubit 是對目的電腦內部結構的完全不透明參考。
Q # 程式無法 introspect 至 qubit 的狀態、其在目的電腦上的標記法，或甚至是與任何其他可供程式使用的 qubit 相同的 qubit。
相反地，程式可以呼叫 `Measure` 之類的作業來從 qubit 中學習資訊，以及呼叫 `X` 和 `H` 等作業來處理 qubit 的狀態。
這些作業在此語言中沒有內建定義，而且只有用來執行特定 Q # 程式的目的電腦才有具體設定。
Q # 程式會依照目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。
如此一來，Q # 可讓您輕鬆地表達基礎配量和混合式量子-傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。

## <a name="q-operations-and-functions"></a>Q # 作業和函數

具體而言，Q # 程式是由一或多個*作業*、一個或多個函*式，以及*使用者定義型別所組成。 作業是用來描述量子機器狀態的轉換，而且是 Q # 程式最基本的建立區塊。 在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括目的電腦所執行的內建*內建函式*作業。
在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。

相對於作業，函數是用來描述純粹的傳統行為，而且除了計算傳統輸出值之外，也不會有任何影響。 問 # 是強型別語言，並隨附一組內建的基本型別，以及使用者定義型別的支援。 

在本指南的其餘部分中，我們將瞭解如何使用不同的語言概念和結構，以協助我們透過作業、函式和類型的基本構件來定義複雜的配量程式。 

## <a name="structure-of-q-source-files"></a>Q # 來源檔案的結構

問 # 來源檔案至少包含*命名空間*宣告，此宣告會指定 .net 命名空間，其中包含來源檔案中的定義。
您可以使用 `open` 語句，來包含來自其他 Q # 來源檔案和程式庫的定義。
例如，定義基本閘道的大部分作業都是在 <xref:microsoft.quantum.intrinsic> 命名空間中定義。
為了讓程式碼能夠使用這項功能，我們只要在每個檔案的頂端 `open` 該命名空間：

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

在命名空間中，每個 Q # 來源檔案都可以定義*作業*、*函式*和*使用者定義類型*的任何組合。
在本節的其餘部分，我們將逐一說明每個專案，並提供如何在實務中使用它們來建立有用的量副程式的範例。
