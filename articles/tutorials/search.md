---
title: 以 Q# 執行格羅弗搜尋演算法 - Quantum Development Kit
description: 建置一個 Q# 專案以示範格羅弗演算法，此為標準量子演算法之一。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9e4c53b4d5159cf07f0654603c1d477ad09eb7c6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274347"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>教學課程：以 Q\# 執行格羅弗搜尋演算法

在本教學課程中，您可以了解如何建立及執行格羅弗搜尋，以加速搜尋非結構化資料。  格羅弗搜尋是最受歡迎的量子運算演算法之一，而這個相對小型的 Q# 實作，可讓您使用高階的 Q# 量子程式設計語言來表達量子運算法，瞭解量子解決方案程式設計的一些優點。  在本指南最後，您會看到模擬輸出示範了如何在有序項目清單中成功地搜尋特定字串，且花費的時間比古典電腦搜尋所需的少了許多。

格羅弗演算法會搜尋特定項目的非結構化資料清單。 例如，它可以回答問題：從一副牌中抽出的這張牌是紅心 A 嗎？ 為特定項目的加上標籤，稱為_標記輸入_。

使用格羅弗搜尋演算法，可保證量子電腦在執行此搜尋時所使用的步驟必定會比您搜尋清單中的項目數少 — 這是任何傳統演算法都做不到的。 以一副牌的案例來說，增加的速度並不多；但清單中若包含數百萬或數十億個項目，就會有很大的差異。

只要幾行程式碼，您就可以建置格羅弗搜尋演算法。

## <a name="prerequisites"></a>必要條件

- Microsoft [Quantum Development Kit][install]。

## <a name="what-does-grovers-search-algorithm-do"></a>格羅弗搜尋演算法有哪些功能？

格羅弗演算法會詢問清單中的某個項目是否為我們要搜尋的項目。 其運作方式是，建構清單索引的量子疊加，並以每個係數 (或機率振幅) 代表該索引就是您要尋找之索引的機率。

此演算法的核心是兩個步驟，會以累加方式提高我們所尋找之索引的係數，直到該係數的機率振幅趨近於一。

遞增的數值會低於清單中的項目數。 正因如此，格羅弗搜尋演算法才能以比任何傳統演算法更少的步驟來執行搜尋。

![格羅弗搜尋演算法的功能圖表](~/media/grover.png)

## <a name="write-the-code"></a>撰寫程式碼

1. 使用 Quantum 開發套件，[為命令列應用程式建立新的 Q# 專案](xref:microsoft.quantum.install.standalone)。 將專案標題命名為 `Grover`。

1. 將下列程式碼新增至新專案中的 `Program.qs` 檔案：

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. 若要定義我們要搜尋的清單，請建立新檔案 `Reflections.qs`，並貼到下列程式碼中：

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` 作業會定義您要搜尋的標記輸入：替代零和一的字串。 此範例會進行標記輸入的硬式編碼，並且可進行擴充以搜尋不同的輸入，或進行一般化以搜尋任何輸入。

1. 接著，執行新的 Q# 程式以尋找 `ReflectAboutMarked` 所標示的項目。

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>具有 Visual Studio 或 Visual Studio Code 的 Q# 命令列應用程式

視專案設定和命令列選項而定，可執行檔將會在模擬器或資源估計工具上執行標記為 `@EntryPoint()` 屬性的作業或函式。

在 Visual Studio 中，只要按 Ctrl + F5 執行指令碼即可。

在 VS Code 中，透過在終端機中輸入下列命令，以第一次建立 `Program.qs`：

```Command line
dotnet build
```

在後續的執行中，不需要重新建立。 若要執行，請輸入下列命令並按 Enter 鍵：

```Command line
dotnet run --no-build
```

您應該會看到顯示在終端機中的下列訊息：

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

這是因為您未指定想要使用的 qubits 數目，所以終端機會告訴您可執行檔的命令。 如果我們想要使用 5 個 qubits，則我們應該輸入：

```Command line
dotnet run --n-qubits 5
```

按 Enter 後您應該會看見下列輸出：

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>後續步驟

如果您喜歡本教學課程，請參閱下列一些資源，以深入了解如何使用 Q# 撰寫您自己的量子應用程式：

- [回到 QDK 使用者入門指南](xref:microsoft.quantum.welcome)
- 試用較一般的格羅弗搜尋演算法[範例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [深入瞭解格羅弗搜尋與 Quantum Katas](xref:microsoft.quantum.overview.katas)
- 深入瞭解[振幅放大][amplitude-amplification]，格羅弗搜尋演算法背後的量子運算技術
- [量子運算概念](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit 範例](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification