---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799154"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安裝 Microsoft Quantum Development Kit (QDK)

了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。 QDK 是由下列各項所組成的：

- Q# 程式設計語言
- 可在 Q# 中抽象呈現複雜功能的一組程式庫
- (以 Python 或 .NET 語言編寫的) 主應用程式，可執行以 Q# 編寫的量子操作。
- 用來協助您進行開發的工具

視您選擇的開發環境而定，安裝步驟會有所不同。 請從下列章節選擇您的環境。

## <a name="develop-with-python"></a>使用 Python 來開發

適用於 Python 的 qsharp 套件可讓您輕鬆地從 Python 內模擬 Q# 作業和函式。 IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的擴充功能，提供編譯和模擬 Q# 作業的核心功能。

1. 先決條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員
    - [.NET Core SDK 3.0 或更新版本](https://www.microsoft.com/net/download)

1. 安裝 `qsharp` 套件

    ```bash
    pip install qsharp
    ```

1. 安裝 `iqsharp` 套件

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
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

        ```bash
        python hello_world.py
        ```

    - 驗證輸出。 您的程式應該會輸出下列幾行：

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>使用 Jupyter 筆記本來開發

Jupyter Notebook 是學術環境、科學實驗室和線上共同作業程式設計的最愛，提供就地程式碼執行，包括 Q# 程式碼，以及各項指示、附註和其他內容。  以下是開始建立您自己的 Q# 筆記本所需的準備工作。

IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。


1. 先決條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 或更新版本](https://www.microsoft.com/net/download)

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

    - 瀏覽至命令列上顯示的 URL。 例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - 使用 Q# 核心建立 Jupyter 筆記本，並將下列程式碼新增至第一個筆記本資料格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 執行筆記本的此一資料格：

        ![Jupyter 筆記本資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        您應該會在資料格的輸出中看到 `SayHello`。 在 Jupyter 筆記本中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。


    - 在新的資料格中，使用 `%simulate` magic 在剛剛建立的作業量子電腦中模擬執行：

        ![Jupyter 筆記本資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>透過 Visual Studio，在 Windows 上使用 C# 來開發

Visual Studio 提供進階的環境來開發 Q# 程式，提供像是程式碼完成和語法反白顯示等實用功能，引導開發人員建置其應用程式。  Q# Visual Studio 擴充功能包含適用於 Q# 檔案的範本、專案以及語法反白顯示和 IntelliSense 支援。


1. 先決條件

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載

1. 安裝 Q# Visual Studio 擴充功能

    - 下載 [Visual Studio 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - 將擴充功能新增至 Visual Studio

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立新的 C# 應用程式

        - 移至 [檔案]   -> [新增]   -> [專案] 
        - 在搜尋方塊中輸入 `Q#`
        - 選取 [Q# 應用程式] 
        - 選取 [**下一步**]
        - 選擇應用程式的名稱和位置
        - 選取 [建立] 

    - 檢查專案

        您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。

    - 執行應用程式

        - 選取 [偵錯]   -> [啟動但不偵錯] 
        - 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> * 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  

## <a name="develop-with-c-using-visual-studio-code"></a>使用 Visual Studio Code，透過 C# 開發

Visual Studio Code (VS Code) 提供進階的環境跨多個電腦環境來開發 Q# 程式，包括 Windows、Linux 和 Mac，提供像是程式碼完成和語法反白顯示等實用功能，引導開發人員建置其應用程式。  Q# VS Code 擴充功能包含語法反白顯示，以及 Q# 程式碼片段。

1. 先決條件

   - [VS 程式碼](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 或更新版本](https://www.microsoft.com/net/download)

1. 安裝 Quantum VS Code 擴充功能

    - 安裝 [VS Code 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. 安裝 Quantum 專案範本：

   - 移至 [檢視]   -> [命令選擇區] 
   - 選取 [Q#:  安裝專案範本]

    您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立新專案：

        - 移至 [檢視]   -> [命令選擇區] 
        - 選取 [Q#:  建立新專案]
        - 瀏覽至您要建立應用程式的檔案系統位置
        - 專案建立好之後，請按一下 [開啟新專案...]  按鈕

    - 執行應用程式：

        - 移至 [偵錯]   -> [啟動但不偵錯] 
        - 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`

> [!NOTE]
> * > * Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>透過 `dotnet` 命令列工具，使用 C# 來開發

當然，您也可以從命令列建置並執行 Q# 程式，只要安裝 .NET Core SDK 和 QDK 專案範本即可。 

1. 先決條件

    - [.NET Core SDK 3.0 或更新版本](https://www.microsoft.com/net/download)

1. 安裝適用於 .NET 的 Quantum 專案範本

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立新的應用程式

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - 瀏覽至新的應用程式目錄

       ```bash
       cd runSayHello
       ```

    您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。

    - 執行應用程式

        ```bash
        dotnet run
        ```

        您應該會看見下列輸出：`Hello quantum world!`

## <a name="whats-next"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。
