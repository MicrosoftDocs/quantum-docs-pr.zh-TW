---
title: 使用 Q# Jupyter Notebook 開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274033"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q# Jupyter Notebook 開發

安裝 QDK 以在 Q# Jupyter Notebook 上開發 Q# 作業。

Jupyter Notebook 允許就地執行指示、備註與其他內容旁的程式碼。 此環境適用於撰寫含內嵌說明或配量運算互動式教學課程的 Q# 程式碼。 以下是開始建立您自己的 Q# 筆記本所需的準備工作。

IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。

> [!NOTE]
> * 在 Q# Jupyter Notebook 中，您只可以執行 Q# 程式碼，且無法從外部主機程式 (例如 Python 或 C# 檔案) 呼叫作業。 如果您的目標是將外部傳統主機程式與配量程式結合，則此環境不適合。

1. 必要條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. 安裝 `iqsharp` 套件

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > 如果在進行 `dotnet iqsharp install` 步驟期間發生錯誤，請開啟新的終端機視窗，然後再試一次。
    > 如果仍無法解決問題，請嘗試找到已安裝的 `dotnet-iqsharp` 工具 (在 Windows 上則為 `dotnet-iqsharp.exe`)，並執行：
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > 其中的 `/path/to/dotnet-iqsharp` 應以您檔案系統中 `dotnet-iqsharp` 工具的絕對路徑加以取代。
    > 此工具通常位於您使用者設定檔資料夾中 `.dotnet/tools` 的下方。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 執行下列命令以啟動筆記本伺服器：

        ```
        jupyter notebook
        ```

    - 若要開啟 Jupyter Notebook，請複製命令列所提供的 URL，並貼到您的瀏覽器中。

    - 使用 Q# 核心建立 Jupyter Notebook，並將下列程式碼新增至第一個筆記本資料格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 執行筆記本的此一資料格：

        ![Jupyter Notebook 資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        您應該會在資料格的輸出中看到 `SayHello`。 在 Jupyter Notebook 中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。


    - 在新的資料格中，使用 `%simulate` 命令來執行您剛才建立的作業 (在模擬器中)：

        ![Jupyter Notebook 資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        您應該會在畫面上看見列印的訊息，以及所叫用作業的結果 (在此我們看到空白的元組 `()`，因作業只傳回 `Unit` 型別)。

## <a name="next-steps"></a>後續步驟

您已安裝 Q# Jupyter Notebook 適用的 QDK，現在您可以撰寫並執行[第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)，方法是直接在 Jupyter Notebook 環境中撰寫您的 Q # 程式碼。

如需更多如何使用 Q# Jupyter Notebook 的範例，請參閱：
- [Q# 與 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) \(英文\)。 在此您將找到 Q# Jupyter Notebook，其中顯示如何在此環境中使用 Q#。
- [Quantum Katas](xref:microsoft.quantum.overview.katas)，這是一系列開放原始碼的自學型教學課程，含一組程式設計練習，以 Q# Jupyter Notebook 格式呈現。 [Quantum Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是很好的起點。 Quantum Katas 的目標是要同時讓您學會配量運算和 Q# 程式設計的要素。 這些要素是使用 Q# Jupyter Notebook 所能建立內容種類的絕佳範例。
