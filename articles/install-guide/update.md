---
title: 瞭解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819734"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。

本文假設您已安裝 QDK。 如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。

我們建議您隨時掌握最新的 QDK 版本。 遵循此更新指南以升級至最新的 QDK 版本。 此套裝程式含兩個部分：
1. 更新您現有的 Q # 檔案和專案，以將您的程式碼與任何更新的語法對齊
2. 為您選擇的開發環境更新 QDK 本身 

## <a name="updating-q-projects"></a>更新 Q # 專案 

無論您使用C#的是或 Python 來裝載 q # 作業，請遵循這些指示來更新您的 q # 專案。

1. 首先，檢查您是否有最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示字元中執行下列命令：
    ```bash
    dotnet --version
    ```
確認輸出 `3.1.100` 或更高。 如果不是，請安裝[最新版本](https://dotnet.microsoft.com/download)，然後再檢查一次。 然後根據您的設定（Visual Studio、Visual Studio Code 或直接命令列）遵循下列指示。

### <a name="update-q-projects-in-visual-studio"></a>更新 Visual Studio 中的 Q # 專案
 
1. 更新至最新版本的 Visual Studio 2019，如需指示，請參閱[這裡](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)
2. 在 Visual Studio 中開啟您的方案
3. 從功能表中，選取 [**組建**] -> [**清除方案**]
4. 在您的 .csproj 檔案中，將目標 framework 更新為 `netcoreapp3.0` （如果是程式庫專案，則會 `netstandard2.1`）。
    也就是，編輯表單的行：
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。
5. 儲存並關閉方案中的所有檔案
6. 選取 [**工具**] -> **命令列** -> **開發人員命令提示字元**
7. 針對方案中的每個專案，執行下列命令：
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    如果您的專案使用任何其他的 Microsoft 量子套件（例如，Microsoft 量子. 數值），請執行下列命令。
8. 關閉命令提示字元，然後選取 [**組建** -> **組建方案**] （*請勿選取 [* 重建方案]，因為重建將一開始就會失敗）

您現在可以直接跳至[更新您的 VISUAL STUDIO QDK 延伸](#update-visual-studio-qdk-extension)模組。


### <a name="update-q-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q # 專案

1. 在 Visual Studio Code 中，開啟包含要更新之專案的資料夾
2. 選取 [**終端**機] -> **新的終端**機
3. 遵循使用命令列進行更新的指示（如下所示）

### <a name="update-q-projects-using-the-command-line"></a>使用命令列更新 Q # 專案

1. 流覽至包含您專案檔的資料夾
2. 執行以下命令：
    ```bash
    dotnet clean [project_name].csproj
    ```

3. 在您的 .csproj 檔案中，將目標 framework 更新為 `netcoreapp3.0` （如果是程式庫專案，則會 `netstandard2.1`）。
    也就是，編輯表單的行：
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。
4. 執行以下命令：
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    如果您的專案使用任何其他的 Microsoft 量子套件（例如，Microsoft 量子. 數值），請同時執行命令。
5. 儲存並關閉所有檔案。
6. 針對每個專案相依性重複1-4，然後流覽回到包含主要專案的資料夾，並執行：
    ```bash
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
* [命令列和C#：更新專案範本](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>更新適用于 Python 的 IQ #

1. 更新 `iqsharp` 核心 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 確認 `iqsharp` 版本

    ```bash
    dotnet iqsharp --version
    ```

    您應該會看見下列輸出：

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    如果您的 `iqsharp` 版本較高，請不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。

3. 更新 `qsharp` 封裝

    ```bash
    pip install qsharp --upgrade
    ```

4. 確認 `qsharp` 版本

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
5. 從 `.qs` 檔案的位置執行下列命令
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. 您現在可以使用更新的 QDK 版本來執行現有的量副程式。

### <a name="update-iq-for-jupyter-notebooks"></a>更新 Jupyter 筆記本的 IQ #

1. 更新 `iqsharp` 核心

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 確認 `iqsharp` 版本

    ```bash
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

   - 移至 [檢視] -> [命令選擇區]
   - 選取 [ **Q #：安裝專案範本**]
   - 幾秒鐘之後，您應該會看到快顯確認「專案範本安裝成功」的快顯視窗

### <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令列工具

1. 更新 .NET 的量子專案範本

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>接下來呢？

既然您已在慣用的環境中更新配量開發工具組，您可以繼續開發和執行您的量副程式。 如果您尚未撰寫程式，您可以開始使用[第一個量副程式](xref:microsoft.quantum.write-program)。
