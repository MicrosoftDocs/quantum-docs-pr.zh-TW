---
title: 使用 Q# 和 Python 進行開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274029"
---
# <a name="develop-with-q-and-python"></a>使用 Q# 和 Python 進行開發

安裝 QDK 來開發 Python 主機程式，以呼叫 Q # 作業。

1. 必要條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. 安裝 `qsharp` 封裝，此為允許 Q# 和 Python 之間互通的 Python 封裝。

    ```
    pip install qsharp
    ```

1. 安裝 IQ#，此為 Jupyter 與 Python 所使用的核心，可提供用於編譯與執行 Q# 作業的核心功能。

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
  
1. 雖然您可以在任何 IDE 中將 Q # 搭配 Python 使用，但強烈建議使用 Q # + Python 應用程式適用的 Visual Studio Code (VS Code) IDE。 透過使用 Visual Studio Code 與 QDK Visual Studio Code 擴充功能，您可以存取豐富的功能。

    - 安裝 [VS Code](https://code.visualstudio.com/download) (Windows、Linux 和 Mac)
    - 安裝 [VS Code 適用的 QDK 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - 建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - 執行程式：

        ```
        python hello_world.py
        ```

    - 驗證輸出。 您的程式應該會輸出下列幾行：

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * 您也可以使用 Python Jupyter Notebook 來撰寫傳統的 Python 程式，並從資料格呼叫 Q# 作業。 Python 程式碼只是一般的 Python 程式。

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
