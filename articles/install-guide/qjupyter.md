---
title: 使用 Q# Jupyter Notebooks 來開發
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630340"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q# Jupyter Notebooks 來開發

安裝 QDK 以在 Q # Jupyter 筆記本上開發 Q # 作業。

Jupyter 筆記本允許就地執行程式碼，連同指示、附注和其他內容。 此環境適合用內嵌的說明或量子計算互動式教學課程來撰寫 Q # 程式碼。 以下是開始建立您自己的 Q# 筆記本所需的準備工作。

IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。

> [!NOTE]
> * 在 [Q # Jupyter 筆記本] 中，您只能執行 Q # 程式碼，而且無法從外部主機程式（例如 Python 或 c # 檔案）呼叫作業。 如果您的目標是要將外部傳統主機程式與配量程式合併，則此環境不適用。

1. 必要條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3。1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. 安裝 `iqsharp` 套件

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > 如果您在步驟中收到錯誤 `dotnet iqsharp install` ，請開啟新的終端機視窗，然後再試一次。
    > 如果仍然無法運作，請嘗試尋找已安裝的 `dotnet-iqsharp` 工具（在 Windows 上 `dotnet-iqsharp.exe` ），並執行：
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > 其中， `/path/to/dotnet-iqsharp` 應取代為 `dotnet-iqsharp` 檔案系統中工具的絕對路徑。
    > 這通常會在 `.dotnet/tools` 您的使用者設定檔資料夾中。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 執行下列命令以啟動筆記本伺服器：

        ```
        jupyter notebook
        ```

    - 若要開啟 Jupyter Notebook，請將命令列所提供的 URL 複製並貼到您的瀏覽器中。

    - 使用 Q # 核心建立 Jupyter Notebook，並將下列程式碼新增至第一個筆記本資料格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 執行筆記本的此一資料格：

        ![使用 Q # 程式碼 Jupyter Notebook 儲存格](~/media/install-guide-jupyter.png)

        您應該會在資料格的輸出中看到 `SayHello`。 在 Jupyter Notebook 中執行時，會編譯 Q # 程式碼，而筆記本會輸出找到的作業名稱。


    - 在新的資料格中，使用命令執行您剛才建立的作業（在模擬器中） `%simulate` ：

        ![具有% 模擬魔術的 Jupyter Notebook 資料格](~/media/install-guide-jupyter-simulate.png)

        您應該會看到訊息印在畫面上，以及您叫用之作業的結果（在這裡，我們會看到空白的元組，因為我們的作業只會傳回 `()` `Unit` 類型）。

## <a name="next-steps"></a>後續步驟

現在您已安裝了 Q # Jupyter 筆記本的 QDK，您可以撰寫並執行[您的第一個量副程式](xref:microsoft.quantum.quickstarts.qrng)，方法是直接在 Jupyter Notebook 環境中撰寫您的 Q # 程式碼。

如需如何使用 Q # Jupyter 筆記本的更多範例，請參閱：
- [問答 # 和 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。 您會在這裡找到一個 Q # Jupyter Notebook，說明如何在此環境中使用 Q #。
- [量子 Katas](xref:microsoft.quantum.overview.katas)，這是一個開放原始碼集合，可自主教學課程和一組程式設計練習，以 Q # Jupyter 筆記本形式呈現。 [量子 Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是不錯的起點。 量子 Katas 的目標在於教您同時進行量子運算和 Q # 程式設計的要素。 這些是您可以使用 Q # Jupyter 筆記本建立之內容種類的絕佳範例。
