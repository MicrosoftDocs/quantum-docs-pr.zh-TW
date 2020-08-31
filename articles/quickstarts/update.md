---
title: 更新 Quantum Development Kit (QDK)
description: 說明如何將您的 Q# 專案和 Microsoft Quantum 開發套件更新為目前的版本。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 84782d1628dd100c0939b2b12aa0a9aa8ab2b80e
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863650"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit (QDK)

深入了解如何將 Microsoft Quantum Development Kit (QDK) 更新為最新的版本。

本文假設您已經安裝 QDK。 如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。

我們建議您保持最新的 QDK 版本。 請遵循此更新指南升級至最新的 QDK 版本。 此流程由兩個部分組成：
1. 更新您現有的 Q# 檔案和專案，讓您的程式碼與任何更新後的語法一致。
2. 為您選擇的開發環境更新 QDK 本身。

## <a name="updating-no-locq-projects"></a>更新 Q# 專案 

無論您使用 C# 或 Python 來裝載 Q# 作業，均應依照下列指示更新您的 Q# 專案。

1. 首先，檢查您是否有最新版的 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示字元中執行下列命令：

    ```dotnetcli
    dotnet --version
    ```

    確認輸出為 `3.1.100` 或更新版本。 如果不是，請安裝[最新版本](https://dotnet.microsoft.com/download)，然後再檢查一次。 接著，根據您的設定 (Visual Studio、Visual Studio Code 或直接從命令提示字元) 遵循下列指示進行。

### <a name="update-no-locq-projects-in-visual-studio"></a>更新 Visual Studio 中的 Q# 專案
 
1. 更新為最新版的 Visual Studio 2019，請參閱[此處](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)以取得指示。
2. 在 Visual Studio 中開啟方案。
3. 從功能表中選取 [組建] -> [清除方案]。
4. 在每個 .csproj 檔案中，將目標框架變更為 `netcoreapp3.1` (若為程式庫專案，則變更為 `netstandard2.1`)。
    亦即編輯表單的行：

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    您可以在[此處](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)取得更多關於指定目標框架的詳細資料。

5. 在每個 .csproj 檔案中，將 SDK 設定為 `Microsoft.Quantum.Sdk`，如下行所示。 請注意，版本號碼應該是最新可用的版本，您可以查看[版本資訊](https://docs.microsoft.com/quantum/relnotes/)來判斷。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. 儲存並關閉解決方案中所有的檔案。

7. 選取 [工具] -> [命令列] -> [開發人員命令提示字元]。 或者，您可以使用 Visual Studio 中的封裝管理主控台。

8. 針對解決方案中的每個專案，執行下列命令以**移除**此封裝：

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   如果您的專案使用任何其他的 Microsoft.Quantum 或 Microsoft.Azure.Quantum 封裝 (例如 Microsoft.Quantum.Numerics)，請為這些封裝執行 **add** 命令以更新所使用的版本。

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. 關閉命令提示字元，然後選取 [組建] -> [組建方案] (請*勿*選取 [重建方案])。

您現在可以直接跳到[更新 Visual Studio QDK 擴充功能](#update-visual-studio-qdk-extension)。


### <a name="update-no-locq-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q# 專案

1. 在 Visual Studio Code 中，開啟包含所要更新專案的資料夾。
2. 選取 [終端機] -> [新增終端機]。
3. 請遵循下列指示 (正下方) 以使用命令提示字元進行更新。

### <a name="update-no-locq-projects-using-the-command-prompt"></a>使用命令提示字元更新 Q# 專案

1. 瀏覽至包含您主要專案檔的資料夾。

2. 執行以下命令：

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 判斷 QDK 目前的版本。 若要找到它，您可以參閱[版本資訊](https://docs.microsoft.com/quantum/relnotes/)。 版本格式類似於 `0.12.20072031`。

4. 在您的每個 `.csproj` 檔案中，進行以下步驟：

    - 將目標框架變更為 `netcoreapp3.1` (若為程式庫專案，則變更為 `netstandard2.1`)。 亦即編輯表單的行：

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        您可以在[此處](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)取得更多關於指定目標框架的詳細資料。

    - 取代專案定義中的 SDK 參考。 請確定版本號碼符合您在**步驟 3** 中判斷出的值。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - 移除封裝 `Microsoft.Quantum.Development.Kit` 的參考 (如果有的話)，這將在以下輸入中指定：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - 將所有 Microsoft Quantum 封裝的版本更新為最新發行 QDK 版本 (在**步驟 3** 中判斷的版本)。 這些封裝以下列模式命名：

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        封裝的參考格式如下：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - 儲存更新的檔案。

    - 執行下列動作還原專案的相依性：

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. 瀏覽至包含您主要專案的資料夾，然後執行：

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

現在您的 Q# 專案已更新，請依照下列指示更新 QDK 本身。

## <a name="updating-the-qdk"></a>更新 QDK

更新 QDK 的流程會視開發語言和環境而有所不同。
於下方選取您的開發環境。

* [Python：更新 `qsharp` 套件](#update-the-qsharp-python-package)
* [Jupyter Notebook：更新 IQ# 核心](#update-the-iq-jupyter-kernel)
* [Visual Studio：更新 QDK 擴充功能](#update-visual-studio-qdk-extension)
* [VS Code：更新 QDK 擴充功能](#update-vs-code-qdk-extension)
* [命令列和 C#：更新專案範本](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>更新 `qsharp` Python 套件

更新程式取決於您最初是使用 conda 或 .NET CLI 和 pip 進行安裝。

#### <a name="update-using-conda-recommended"></a>[使用 conda 更新 (建議做法)](#tab/tabid-conda)

1. 啟動您安裝 `qsharp` 套件的 conda 環境，然後執行此命令來更新：

    ```
    conda update -c quantum-engineering qsharp
    ```

1. 從 `.qs` 檔案的位置執行下列命令：

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[使用 .NET CLI 和 pip 更新 (進階做法)](#tab/tabid-dotnetcli)

1. 更新 `iqsharp` 核心 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 確認 `iqsharp` 版本

    ```dotnetcli
    dotnet iqsharp --version
    ```

    您應該會看見下列輸出：

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    如果您的 `iqsharp` 版本較高，別擔心。 其應該符合[最新版本](xref:microsoft.quantum.relnotes)。

1. 更新 `qsharp` 套件：

    ```
    pip install qsharp --upgrade
    ```

1. 確認 `qsharp` 的版本：

    ```
    pip show qsharp
    ```

    您應該會看見下列輸出：

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. 從 `.qs` 檔案的位置執行下列命令：

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

現在您可以使用更新後的 `qsharp` Python 套件來執行現有的量子程式。

### <a name="update-the-ino-locq-jupyter-kernel"></a>更新 IQ# Jupyter 核心

更新程式取決於您最初是使用 conda 或 .NET CLI 和 pip 進行安裝。

#### <a name="update-using-conda-recommended"></a>[使用 conda 更新 (建議做法)](#tab/tabid-conda)

1. 啟動您安裝 `qsharp` 套件的 conda 環境，然後執行此命令來更新：

    ```
    conda update -c quantum-engineering qsharp
    ```

1. 從您現有的每個 Q# Jupyter Notebook 中的資料格執行下列命令：

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[使用 .NET CLI 和 pip 更新 (進階做法)](#tab/tabid-dotnetcli)

1. 更新 `Microsoft.Quantum.IQSharp` 套件：

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 確認 `iqsharp` 的版本：

    ```dotnetcli
    dotnet iqsharp --version
    ```

    您的輸出應該類似如下範例：

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    如果您的 `iqsharp` 版本較高，別擔心。 其應該符合[最新版本](xref:microsoft.quantum.relnotes)。

1. 從您現有的每個 Q# Jupyter Notebook 中的資料格執行下列命令：

    ```
    %workspace reload
    ```

***

您現在可以使用更新後的 IQ# 核心來執行現有的 Q# Jupyter Notebook。

### <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 擴充功能

1. 更新 Q# Visual Studio 擴充功能

    - Visual Studio 會提示您接受 [Quantum Visual Studio 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新
    - 接受更新

    > [!NOTE]
    > 系統會以擴充功能更新專案範本。 更新後的範本只會套用到新建立的專案。 更新擴充模組時，不會更新現有專案的程式碼。

### <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 擴充功能

1. 更新 Quantum VS Code 擴充功能

    - 重新啟動 VS Code
    - 瀏覽至 [擴充功能] 索引標籤
    - 選取 [Microsoft Quantum Development Kit for Visual Studio Code] 擴充功能
    - 重新載入擴充功能

### <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令列工具

1. 更新適用於 .NET 的 Quantum 專案範本

    從命令提示字元：

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   或者，如果您想要使用命令列範本，而且已經安裝 VS Code QDK 延伸模組，您可以從擴充功能本身更新專案範本：

   - [更新 QDK 擴充功能](#update-vs-code-qdk-extension)
   - 在 VS Code 中，前往 [檢視] -> [命令選擇區]
   - 選取 **Q#：安裝命令列專案範本**
   - 幾秒鐘之後，您應該會看到一個快顯視窗確認「專案範本安裝成功」
