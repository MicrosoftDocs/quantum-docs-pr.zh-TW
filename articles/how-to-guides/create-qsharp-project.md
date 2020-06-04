---
title: '瞭解如何使用量子開發工具組（QDK）建立問 # 專案'
description: '使用您選擇的開發環境中的 QDK 和 Q #，初始化專案以進行量子開發'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327521"
---
# <a name="create-a-q-project-in-your-development-environment"></a>在開發環境中建立 Q # 專案

瞭解如何使用 QDK 建立 Q # 專案。

Q # 專案包含包含量子代碼的 Q # 檔案，以及執行配量程式的主機程式。 您可以用 .NET 語言（例如 c #）或 Python 撰寫主機程式。 您也可以使用 IQ # kernel 在 Jupyter Notebook 中執行 Q # 程式碼。

從下列各節選擇您的開發環境和語言：

* [Python](#create-a-python-project)
* [Q# Jupyter Notebook](#create-a-q-jupyter-notebook-project)
* [C # 與 Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C # 與 VS Code](#create-a-c-project-using-vs-code)
* [C # 與命令列](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>建立 Python 專案

1. 必要條件

     * 安裝[適用于 Python 的量子開發工具組](xref:microsoft.quantum.install.python)

1. 為您的專案建立資料夾，並流覽至該資料夾

1. 建立名為的 Q # 檔案 `Operation.qs` ，並在其中新增您的 q # 程式碼。 例如：

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. 建立名為的 python 主機檔案 `host.py` ，以呼叫您的 Q # 作業。 例如：

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. 執行程式：

    ```bash
    python host.py
    ```

1. 驗證輸出。 您的程式應該會輸出下列幾行：

    ```bash
    Hello from quantum world!
    0
    ```

您現在可以繼續開發您的「量子」程式。

## <a name="create-a-q-jupyter-notebook-project"></a>建立 Q # Jupyter Notebook 專案

1. 必要條件

    * 安裝[適用于 Jupyter 筆記本的量子開發工具組](xref:microsoft.quantum.install.jupyter)

1. 執行下列命令以啟動筆記本伺服器：

    ```bash
    jupyter notebook
    ```

1. 瀏覽至命令列上顯示的 URL。 例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Jupyter 頁面會出現在瀏覽器中。 **在 [檔案**] 索引標籤上，選取 [**新增**  >  **q #** ] 以建立具有 Q # 核心的 Jupyter Notebook。 將下列程式碼新增至第一個筆記本資料格：

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. 選取 [**儲存格**] [  >  **執行單元**格] 以執行筆記本。 `SayHello`很快就會出現在資料格的輸出中：

    ![使用 Q # 程式碼 Jupyter Notebook 儲存格](~/media/install-guide-jupyter.png)

    在 Jupyter 筆記本中執行時，會編譯 Q # 程式碼，而筆記本會輸出找到的作業名稱。

1. 在新的資料格中，使用 `%simulate` magic 在剛剛建立的作業量子電腦中模擬執行：

    ![具有% 模擬魔術的 Jupyter Notebook 資料格](~/media/install-guide-jupyter-simulate.png)

    You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).

您現在可以新增其他的 Q # 作業，以繼續進行您的量子開發。

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>使用 Visual Studio 在 Windows 上建立 c # 專案

1. 必要條件

    * 安裝[適用于 Visual Studio 的量子開發工具組擴充](xref:microsoft.quantum.install.cs)功能

1. 建立新的 C# 應用程式

    * 移至 **[** 檔案] [  ->  **新增**  ->  **專案**]
    * 在搜尋方塊中輸入 `Q#`
    * 選取 [Q# 應用程式]****
    * 選取 [**下一步**]
    * 選擇應用程式的名稱和位置
    * 選取 [建立] 

1. 檢查專案

    您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。

1. 執行應用程式

    * 選取 [不進行調試的**Debug**  ->  **啟動**]
    * 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

您現在可以使用 Visual Studio 繼續進行量子開發

> [!NOTE]
> * 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  

## <a name="create-a-c-project-using-vs-code"></a>使用 VS Code 建立 c # 專案

1. 必要條件

    * 安裝[適用于 VS Code 的量子開發工具組擴充](xref:microsoft.quantum.install.cs)功能

1. 建立新專案：

    * 移至**View**  ->  **命令**選擇區
    * 選取 [ **Q #：建立新專案**]
    * 選取**獨立主控台應用程式**
    * 瀏覽至您要建立應用程式的檔案系統位置
    * 專案建立好之後，請按一下 [開啟新專案...]**** 按鈕

1. 執行應用程式：

    * 移至**終端**機  ->  **新終端**機
    * 輸入 `dotnet run`
    * 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`

您現在可以使用 Visual Studio Code 繼續進行量子開發。

> [!NOTE]
> * Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>使用命令列工具建立 c # 專案 `dotnet`

1. 必要條件

    * 安裝[命令列的量子開發工具組](xref:microsoft.quantum.install.standalone)

1. 建立新的應用程式

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. 瀏覽至新的應用程式目錄

    ```bash
    cd <project name>
    ```

    您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。

1. 執行應用程式

    ```dotnetcli
    dotnet run
    ```

    您應該會看見下列輸出：`Hello quantum world!`

您現在可以使用命令列工具繼續進行您的量子開發。

## <a name="next-steps"></a>下一步

現在您已在慣用的環境中建立專案，您可以繼續進行您的量子開發。
