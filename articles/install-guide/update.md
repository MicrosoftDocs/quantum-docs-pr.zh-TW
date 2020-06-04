---
title: 更新量子開發工具組（QDK）
description: '描述如何將您的 Q # 專案和 Microsoft Quantum Development Kit 更新為目前的版本。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327558"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。

本文假設您已安裝 QDK。 如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。

我們建議您隨時掌握最新的 QDK 版本。 遵循此更新指南以升級至最新的 QDK 版本。 此套裝程式含兩個部分：
1. 更新您現有的 Q # 檔案和專案，以將您的程式碼與任何更新的語法對齊。
2. 為您選擇的開發環境更新 QDK 本身。

## <a name="updating-q-projects"></a>更新 Q # 專案 

無論您使用的是 c # 或 Python 來裝載 Q # 作業，請遵循這些指示來更新您的 Q # 專案。

1. 首先，檢查您是否有最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示字元中執行下列命令：

    ```dotnetcli
    dotnet --version
    ```

    確認輸出為 `3.1.100` 或更高。 如果不是，請安裝[最新版本](https://dotnet.microsoft.com/download)，然後再檢查一次。 然後根據您的設定（Visual Studio、Visual Studio Code 或直接命令列）遵循下列指示。

### <a name="update-q-projects-in-visual-studio"></a>更新 Visual Studio 中的 Q # 專案
 
1. 更新至最新版本的 Visual Studio 2019，如需指示，請參閱[這裡](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)。
2. 在 Visual Studio 中開啟方案。
3. 從功能表中，選取 [**組建**] [  ->  **清除方案**]。
4. 在您的 .csproj 檔案中，將目標 framework 更新為 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是程式庫專案）。
    也就是，編輯表單的行：

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。

5. 在每個 .csproj 檔案中，將 SDK 設定為 `Microsoft.Quantum.Sdk` ，如下行所示。 請注意，版本號碼應該是最新可用，而且您可以藉由查看[版本](https://docs.microsoft.com/quantum/relnotes/)資訊來加以判斷。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. 儲存並關閉方案中的所有檔案。

7. 選取 [**工具**] [  ->  **命令列**]  ->  **開發人員命令提示字元**。 或者，您也可以在 Visual Studio 中使用套件管理主控台。

8. 針對方案中的每個專案，執行下列命令以**移除**此套件：

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   如果您的專案使用任何其他的 Microsoft 量子或 Microsoft 量子套件（例如，Microsoft 量子），請針對這些封裝執行 [**新增**] 命令，以更新所使用的版本。

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. 關閉命令提示字元，然後選取 [**組建**]  ->  [ *not*組建**方案**] （請勿選取 [重建方案]）。

您現在可以直接跳至[更新您的 VISUAL STUDIO QDK 延伸](#update-visual-studio-qdk-extension)模組。


### <a name="update-q-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q # 專案

1. 在 Visual Studio Code 中，開啟包含要更新之專案的資料夾。
2. 選取 [**終端**機] [  ->  **新終端**機]。
3. 請遵循使用命令列進行更新的指示（直接如下所示）。

### <a name="update-q-projects-using-the-command-line"></a>使用命令列更新 Q # 專案

1. 流覽至包含主要專案檔的資料夾。

2. 執行以下命令：

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 判斷 QDK 的目前版本。 若要尋找它，您可以參閱[版本](https://docs.microsoft.com/quantum/relnotes/)資訊。 版本會採用類似的格式 `0.11.2006.207` 。

4. 在您的每個檔案中 `.csproj` ，執行下列步驟：

    - 將目標 framework 更新為 `netcoreapp3.1` （ `netstandard2.1` 如果它是程式庫專案，則為）。 也就是，編輯表單的行：

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。

    - 在專案定義中取代 SDK 的參考。 請確定版本號碼對應至**步驟 3**中所判斷的值。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - 移除封裝的參考 `Microsoft.Quantum.Development.Kit` （如果有的話），其將在下列專案中指定：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - 將所有 Microsoft 量子套件的版本更新為最新發行的 QDK 版本（在**步驟 3**中判斷）。 這些套件會使用下列模式來命名：

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        封裝的參考具有下列格式：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - 儲存更新的檔案。

    - 執行下列動作來還原專案的相依性：

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. 流覽回到包含主要專案的資料夾，然後執行：

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

現在您已更新您的 Q # 專案，請遵循下列指示來更新 QDK 本身。

## <a name="updating-the-qdk"></a>更新 QDK

更新 QDK 的程式會根據您的開發語言和環境而有所不同。
請在下方選取您的開發環境。

* [Python：更新 IQ # 擴充功能](#update-iq-for-python)
* [Jupyter 筆記本：更新 IQ # 擴充功能](#update-iq-for-jupyter-notebooks)
* [Visual Studio：更新 QDK 擴充功能](#update-visual-studio-qdk-extension)
* [VS Code：更新 QDK 擴充功能](#update-vs-code-qdk-extension)
* [命令列和 c #：更新專案範本](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>更新適用于 Python 的 IQ #

1. 更新 `iqsharp` 核心 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 驗證 `iqsharp` 版本

    ```dotnetcli
    dotnet iqsharp --version
    ```

    您應該會看見下列輸出：

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    如果您的 `iqsharp` 版本較高，請不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。

3. 更新 `qsharp` 套件

    ```bash
    pip install qsharp --upgrade
    ```

4. 驗證 `qsharp` 版本

    ```bash
    pip show qsharp
    ```

    您應該會看見下列輸出：

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. 從檔案的位置執行下列命令 `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. 您現在可以使用更新的 QDK 版本來執行現有的量副程式。

### <a name="update-iq-for-jupyter-notebooks"></a>更新 Jupyter 筆記本的 IQ #

1. 更新 `iqsharp` 核心

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 驗證 `iqsharp` 版本

    ```dotnetcli
    dotnet iqsharp --version
    ```

    您的輸出應該類似如下範例：

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    如果您的 `iqsharp` 版本較高，請不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。

3. 從您 Jupyter Notebook 中的儲存格執行下列命令：

    ```
    %workspace reload
    ```

4. 您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。

### <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 延伸模組

1. 更新 Q # Visual Studio 延伸模組

    - Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新
    - 接受更新

    > [!NOTE]
    > 專案範本會以擴充功能更新。 更新的範本僅適用于新建立的專案。 更新延伸模組時，不會更新現有專案的程式碼。

### <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 延伸模組

1. 更新 VS Code 延伸模組的量子

    - 重新開機 VS Code
    - 流覽至 [**擴充**功能] 索引標籤
    - 選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**
    - 重載擴充功能

2. 更新 [量子] 專案範本：

   - 移至**View**  ->  **命令**選擇區
   - 選取 [ **Q #：安裝專案範本**]
   - 幾秒鐘之後，您應該會看到快顯確認「專案範本安裝成功」的快顯視窗

### <a name="c-using-the-dotnet-command-line-tool"></a>C #，使用 `dotnet` 命令列工具

1. 更新 .NET 的量子專案範本

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
