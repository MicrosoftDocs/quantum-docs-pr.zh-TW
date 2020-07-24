---
title: 使用 Q# Jupyter Notebook 開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871445"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q# Jupyter Notebook 開發

安裝 QDK 以在 Q# Jupyter Notebook 上開發 Q# 作業。

Jupyter Notebook 允許就地執行指示、備註與其他內容旁的程式碼。 此環境適用於撰寫含內嵌說明或配量運算互動式教學課程的 Q# 程式碼。 以下是開始建立您自己的 Q# 筆記本所需的準備工作。

> [!NOTE]
> * 在 Q# Jupyter Notebook 中，您只可以執行 Q# 程式碼，且無法從外部主機程式 (例如 Python 或 C# 檔案) 呼叫作業。 如果您的目標是將外部傳統主機程式與配量程式結合，則此環境不適合。

## <a name="install-the-iq-jupyter-kernel"></a>安裝 IQ# Jupyter 核心

IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。

### <a name="install-using-conda-recommended"></a>[使用 conda 安裝 (建議做法)](#tab/tabid-conda)

1. 安裝 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。 **注意：** 需要安裝 64 位元。

1. 開啟 Anaconda 提示字元。

   - 或者，您想要使用 PowerShell 或 pwsh：開啟命令介面、執行 `conda init powershell`，然後將命令介面關閉再重新開啟。

1. 執行下列命令，使用必要的套件 (包括 Jupyter Notebook 和 IQ#) 建立並啟動名為 `qsharp-env` 的新 conda 環境：

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. 從相同的終端機執行 `python -c "import qsharp"`，以確認您的安裝，並將所有必要的 QDK 元件填入您的本機套件快取。

### <a name="install-using-net-cli-advanced"></a>[使用 .NET CLI 安裝 (進階做法)](#tab/tabid-dotnetcli)

1. 必要條件：

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. 安裝 `Microsoft.Quantum.IQSharp` 套件。

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

就這麼簡單！ 您現在已有適用於 Jupyter 的 IQ# 核心，其可提供從 Q# Jupyter Notebook 編譯和執行 Q# 作業的核心功能。

## <a name="create-your-first-q-notebook"></a>建立您的第一個 Q# 筆記本

現在您已準備好要藉由撰寫和執行簡單的 Q# 作業來驗證您的 Q# Jupyter Notebook 安裝。

1. 從您在安裝期間建立的環境中 (也就是您所建立的 conda 環境，或安裝 Jupyter 時所使用的 Python 環境)，執行下列命令啟動 Jupyter Notebook 伺服器：

    ```
    jupyter notebook
    ```

    - 如果 Jupyter Notebook 沒有在您的瀏覽器中自動開啟，請將命令列所提供的 URL 複製並貼到瀏覽器中。

1. 選擇 [新增] → [Q#]，使用 Q# 核心建立 Jupyter Notebook，並將下列程式碼加入第一個筆記本資料格：

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. 執行筆記本的此一資料格：

    ![Jupyter Notebook 資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

    您應該會在資料格的輸出中看到 `SampleQuantumRandomNumberGenerator`。 在 Jupyter Notebook 中執行時，系統會編譯 Q# 程式碼，且資料格會輸出其找到的任何作業名稱。

1. 在新的資料格中，使用 `%simulate` 命令來執行您剛才建立的作業 (在模擬器中)：

    ![Jupyter Notebook 資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

    您應該會看到您叫用作業的結果。 在此案例中，因為您的作業會產生隨機結果，所以您會看到螢幕上印出 `Zero` 或 `One` 。 如果您重複執行資料格，應該會看到這兩個結果大約是各一半的時間。

## <a name="next-steps"></a>後續步驟

您已安裝 Q# Jupyter Notebook 適用的 QDK，現在您可以撰寫並執行[第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)，方法是直接在 Jupyter Notebook 環境中撰寫 Q# 程式碼。

如需更多如何使用 Q# Jupyter Notebook 的範例，請參閱：

- [Q# 與 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) \(英文\)。 您會在這裡找到一個 Q# Jupyter Notebook，其中提供如何在 Jupyter 環境中使用 Q# 的詳細資訊。
- [Quantum Katas](xref:microsoft.quantum.overview.katas)，這是一系列開放原始碼的自學型教學課程，含一組程式設計練習，以 Q# Jupyter Notebook 格式呈現。 [Quantum Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是很好的起點。 Quantum Katas 的目標是要同時讓您學會配量運算和 Q# 程式設計的要素。 這些要素是使用 Q# Jupyter Notebook 所能建立內容種類的絕佳範例。
