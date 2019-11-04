---
title: 瞭解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185846"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。

本文假設您已安裝 QDK。 如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。

更新步驟取決於您的開發環境。 從下列各節選擇您的環境。

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. 您現在可以使用更新的 QDK 版本來執行現有的量副程式。

## <a name="jupyter-notebooks"></a>Jupyter Notebook

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. 您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。

## <a name="c-on-windows-using-visual-studio"></a>C#在 Windows 上，使用 Visual Studio

1. 更新 Q # Visual Studio 延伸模組

    - Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新
    - 接受更新

    > [!NOTE]
    > 專案範本會以擴充功能更新。 更新的範本僅適用于新建立的專案。 更新延伸模組時，不會更新現有專案的程式碼。

1. 更新 QDK 套件

    - 開啟現有的應用程式
    - 在 方案總管中選取 相依性
    - 選取 [**管理 NuGet 套件**]
    - 將**Microsoft 量子**套件更新為最新版本

1. 您現在可以使用最新的 QDK 來執行應用程式。

## <a name="c-using-vs-code"></a>C#，使用 VS Code

1. 更新 VS Code 延伸模組的量子

    - 重新開機 VS Code
    - 流覽至 [**擴充**功能] 索引標籤
    - 選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**
    - 重載擴充功能

1. 更新 [量子] 專案範本：

   - 移至**View** -> **命令**選擇區
   - 選取 [ **Q #：安裝專案範本**]

1. 在 VS Code 中開啟現有的應用程式

   - 編輯 .csproj 檔案以加入新的封裝版本

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    如果您使用其他 `Microsoft.Quantum` 套件，也請加以更新。

1. 您現在可以使用更新的 QDK 來執行應用程式

## <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令列工具

1. 更新 .NET 的量子專案範本

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 更新並執行現有的應用程式

    - 更新您應用程式中的 QDK 套件版本

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        如果您的應用程式使用任何其他 `Microsoft.Quantum` 套件，也請加以更新。

    - 執行應用程式

        ```bash
        dotnet run
        ```

    - 您的應用程式將會以新的套件版本執行

## <a name="whats-next"></a>接下來呢？

既然您已在慣用的環境中更新配量開發工具組，您可以繼續開發和執行您的量副程式。 如果您尚未撰寫程式，您可以開始使用[第一個量副程式](xref:microsoft.quantum.write-program)。
