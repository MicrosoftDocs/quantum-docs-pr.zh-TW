---
title: 瞭解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463293"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。

本文假設您已安裝 QDK。 如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。


## <a name="updating-q-projects"></a>更新 Q # 專案 

1. 首先，安裝最新版本的[.NET Core SDK 3.0](https://dotnet.microsoft.com/download) ，並在命令提示字元中執行下列命令：
```bash
dotnet --version
```
 確認輸出為3.0.100 或更高版本，然後根據您的設定遵循下列指示。

### <a name="in-visual-studio"></a>在 Visual Studio 中
 
 1. 更新至最新版本的 Visual Studio 2019，如需指示，請參閱[這裡](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)
 2. 在 Visual Studio 中開啟您的方案
 3. 從功能表中，選取 [組建] > [清除方案] 
 4. 將您的每個 .csproj 檔案中[的目標 Framework 更新](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)為 netcoreapp 3.0 （如果它是程式庫專案，則為 netstandard 2.1）
 5. 儲存並關閉方案中的所有檔案
 6. 選取 [工具] > 命令列 > 開發人員命令提示字元
 7. 針對方案中的每個專案，執行下列命令：
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
如果您的專案使用任何其他的 Microsoft 量子套件，也請針對這些封裝執行命令。 
 8. 關閉命令提示字元，然後選取 [組建 > 組建方案] （*請勿選取 [* 重建方案]，因為重建將一開始就會失敗）

### <a name="in-visual-studio-code"></a>在 Visual Studio Code

1. 在 Visual Studio Code 中，開啟包含要更新之專案的資料夾
1. 選取 [終端機] > 新的終端機
1. 遵循使用命令列進行更新的指示

### <a name="using-the-command-line"></a>使用命令列

1. 流覽至包含您專案檔的資料夾
2. 執行以下命令：
```bash
dotnet clean [project_name].csproj
```

3. 將您的每個 .csproj 檔案中[的目標 Framework 更新](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)為 netcoreapp 3.0 （如果它是程式庫專案，則為 netstandard 2.1）
4. 執行以下命令：
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
如果您的專案使用任何其他的 Microsoft 量子套件，也請對這些封裝執行命令。

5. 儲存並關閉所有檔案
6. 針對每個專案相依性重複1-4，然後流覽回到包含主要專案的資料夾，並執行：
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>更新適用于 Python 的 IQ #

1. 更新 `iqsharp` 核心

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 確認 `iqsharp` 版本

    ```bash
    dotnet iqsharp --version
    ```

    您應該會看見下列輸出：

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. 更新 `qsharp` 封裝

    ```bash
    pip install qsharp --upgrade
    ```

1. 確認 `qsharp` 版本

    ```bash
    pip show qsharp
    ```

    您應該會看見下列輸出：

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. 從 `.qs` 檔案的位置執行下列命令
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. 您現在可以使用更新的 QDK 版本來執行現有的量副程式。

## <a name="update-iq-for-jupyter-notebooks"></a>更新 Jupyter 筆記本的 IQ #

1. 更新 `iqsharp` 核心

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 確認 `iqsharp` 版本

    ```bash
    dotnet iqsharp --version
    ```

    您應該會看見下列輸出：

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. 從您 Jupyter Notebook 中的儲存格執行下列命令：
    ```
    %workspace reload
    ```

1. 您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。

## <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 延伸模組

1. 更新 Q # Visual Studio 延伸模組

    - Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新
    - 接受更新

    > [!NOTE]
    > 專案範本會以擴充功能更新。 更新的範本僅適用于新建立的專案。 更新延伸模組時，不會更新現有專案的程式碼。

## <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 延伸模組

1. 更新 VS Code 延伸模組的量子

    - 重新開機 VS Code
    - 流覽至 [**擴充**功能] 索引標籤
    - 選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**
    - 重載擴充功能

1. 更新 [量子] 專案範本：

   - 移至 [檢視] -> [命令選擇區]
   - 選取 [ **Q #：安裝專案範本**]

## <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令列工具

1. 更新 .NET 的量子專案範本

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>接下來呢？

既然您已在慣用的環境中更新配量開發工具組，您可以繼續開發和執行您的量副程式。 如果您尚未撰寫程式，您可以開始使用[第一個量副程式](xref:microsoft.quantum.write-program)。
