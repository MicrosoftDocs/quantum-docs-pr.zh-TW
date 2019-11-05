---
title: 以 Q# 執行格羅弗搜尋演算法 - Quantum Development Kit
description: 建置一個 Q# 專案以示範格羅弗演算法，此為標準量子演算法之一。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443931"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>快速入門：以 Q# 執行格羅弗搜尋演算法

在本快速入門中，您可以瞭解如何建立及執行格羅弗搜尋，以加速搜尋非結構化資料。  格羅弗搜尋是最受歡迎的量子運算演算法之一，而這個相對小型的 Q# 實作，可讓您使用高階的 Q# 量子程式設計語言來表達量子運算法，瞭解量子解決方案程式設計的一些優點。  在本指南最後，您會看到模擬輸出示範了如何在有序項目清單中成功地搜尋特定字串，且花費的時間比古典電腦搜尋所需的少了許多。

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

1. 使用 Quantum Development Kit，在您選擇的開發環境中[建立新的 Q# 專案](xref:microsoft.quantum.howto.createproject) (名為 `Grover`)。

1. 將下列程式碼新增至新專案中的 `Operations.qs` 檔案：

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. 若要定義我們要搜尋的清單，請建立新檔案 `Reflections.qs`，並貼到下列程式碼中：

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    `ReflectAboutMarked` 作業會定義您要搜尋的標記輸入：替代零和一的字串。 此範例會進行標記輸入的硬式編碼，並且可進行擴充以搜尋不同的輸入，或進行一般化以搜尋任何輸入。

1. 接著，執行新的 Q# 程式以尋找 `ReflectAboutMarked` 所標示的項目。

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[使用 Visual Studio Code 或命令列的 Python](#tab/tabid-python)

    若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    然後，您可以從命令列執行 Python 主機程式：

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[使用 Visual Studio Code 或命令列的 C#](#tab/tabid-csharp)

    若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    然後，您可以從命令列執行 C# 主機程式：

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[使用 Visual Studio 2019 的 C#](#tab/tabid-vs2019)

    若要從 Visual Studio 中的 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示下列結果： 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    `ReflectAboutMarked` 作業僅呼叫了四次，但您的 Q# 程式就能從 $2^{5} = 32$ 個可能的輸入中找出 "01010" 輸入！

## <a name="next-steps"></a>後續步驟

如果您喜歡本快速入門，請參閱下列一些資源，以深入了解如何使用 Q# 撰寫您自己的量子應用程式：

- [回到 QDK 使用者入門指南](xref:microsoft.quantum.welcome)
- 試用較一般的格羅弗搜尋演算法[範例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [深入瞭解格羅弗搜尋與 Quantum Katas](xref:microsoft.quantum.overview.katas)
- 深入瞭解[振幅放大](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)，格羅弗搜尋演算法背後的量子運算技術
- [量子運算概念](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit 範例](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
