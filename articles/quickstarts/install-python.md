---
title: 使用 Q# 和 Python 進行開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885525"
---
# <a name="develop-with-q-and-python"></a>使用 Q# 和 Python 進行開發

安裝 QDK 來開發 Python 主機程式，以呼叫 Q # 作業。

## <a name="install-the-qsharp-python-package"></a>安裝 `qsharp` Python 套件

### <a name="install-using-conda-recommended"></a>[使用 conda 安裝 (建議做法)](#tab/tabid-conda)

1. 安裝 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。

1. 開啟 Anaconda 提示字元。

   - 或者，您想要使用 PowerShell 或 pwsh：開啟命令介面、執行 `conda init powershell`，然後將命令介面關閉再重新開啟。

1. 執行下列命令，使用必要的套件 (包括 Jupyter Notebook 和 IQ#) 建立並啟動名為 `qsharp-env` 的新 conda 環境：

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. 從相同的終端機執行 `python -c "import qsharp"`，以確認您的安裝，並將所有必要的 QDK 元件填入您的本機套件快取。

### <a name="install-using-net-cli-and-pip-advanced"></a>[使用 .NET CLI 和 pip 安裝 (進階做法)](#tab/tabid-dotnetcli)

1. 必要條件：

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
    
***

就這麼簡單！ 您現在已有 `qsharp` Python 套件和適用於 Jupyter 的 IQ# 核心，它們可提供從 Python 編譯和執行 Q# 作業的核心功能，並可讓您使用 Q# Jupyter Notebook。

## <a name="choose-your-ide"></a>選擇您的整合式開發環境 (IDE)

雖然您可以在任何 IDE 中將 Q # 搭配 Python 使用，但強烈建議使用 Q # + Python 應用程式適用的 Visual Studio Code (VS Code) IDE。 有了 QDK Visual Studio Code 擴充功能，您就可以存取更豐富的功能，例如警告、語法反白顯示、專案範本等等。

如果您想要使用 VS Code：

- 安裝 [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac)。
- 安裝 [VS Code 適用的 QDK 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

如果您想要使用其他的編輯器，遵循上述指示就夠了。

## <a name="write-your-first-q-program"></a>撰寫您的第一個 Q# 程式

現在您已準備好要藉由撰寫和執行簡單的 Q# 程式來確認您的 `qsharp` Python 套件安裝。

1. 建立一個最小的 Q# 作業，方法是建立名為 `Operation.qs` 的檔案，再於其中加入下列程式碼：

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. 在與 `Operation.qs` 相同的資料夾中，建立名為 `host.py` 的 Python 程式來模擬 Q# `SampleQuantumRandomNumberGenerator()` 作業：

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. 從您在安裝期間建立的環境中 (也就是您安裝 `qsharp` 的 conda 環境或 Python 環境) 執行程式：

    ```
    python host.py
    ```

1. 您應該會看到您叫用作業的結果。 在此案例中，因為您的作業會產生隨機結果，所以您會看到螢幕上列印出 `Zero` 或 `One` 。 如果您重複執行程式，應該會看到這兩個結果大約是各一半的時間。

> [!NOTE]
> * Python 程式碼只是一般的 Python 程式。 您可以使用任何 Python 環境 (包括以 Python 為基礎的 Jupyter Notebook) 來撰寫 Python 程式並呼叫 Q# 作業。 Python 程式可以從與 Python 程式碼本身相同資料夾的任何 .qs 檔案匯入 Q# 作業。

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，接下來可以遵循此指南開始撰寫及執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。