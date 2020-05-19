---
title: '使用 Q # Jupyter 筆記本進行開發'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551034"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q # Jupyter 筆記本進行開發

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

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 建立 `Hello World` 應用程式來驗證安裝

    - 執行下列命令以啟動筆記本伺服器：

        ```bash
        jupyter notebook
        ```

    - 若要開啟 Jupyter 筆記本，請將命令列所提供的 URL 複製並貼到您的瀏覽器中。

    - 使用 Q# 核心建立 Jupyter 筆記本，並將下列程式碼新增至第一個筆記本資料格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 執行筆記本的此一資料格：

        ![Jupyter 筆記本資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        您應該會在資料格的輸出中看到 `SayHello`。 在 Jupyter 筆記本中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。


    - 在新的資料格中，使用命令執行您剛才建立的作業（在模擬器中） `%simulate` ：

        ![Jupyter 筆記本資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        您應該會看到訊息印在畫面上，以及您叫用之作業的結果（在這裡，我們會看到空白的元組，因為我們的作業只會傳回 `()` `Unit` 類型）。

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
