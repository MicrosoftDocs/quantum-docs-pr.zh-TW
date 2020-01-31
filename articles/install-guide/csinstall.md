---
title: '使用 Q # + 進行開發C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831013"
---
# <a name="develop-with-q--c"></a>使用 Q # + 進行開發C#

安裝 QDK 以開發C#主機程式，以呼叫 Q # 作業。

問 # 的設計可與 .NET 語言搭配使用，特別是C#。 您可以在不同的開發環境中使用此配對：

- [使用 Visual Studio 的C# Q # + （Windows）](#VS)
- [使用 Visual Studio Code 的C# Q # + （Windows、Linux 和 Mac）](#VSC)
- [使用 `dotnet` 命令C#行工具的 Q # +](#command)

## 使用 Visual Studio 的 Q # C# + 進行開發<a name="VS"></a>

Visual Studio 提供開發 Q # 程式的豐富環境。 Q # Visual Studio 延伸模組包含 Q # 檔案和專案的範本，以及語法醒目提示、程式碼完成和 IntelliSense 支援。


1. 必要條件

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載

1. 安裝 Q# Visual Studio 擴充功能

    - 下載並安裝[Visual Studio 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)功能

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立新的 C# 應用程式

        - 移至 [檔案] -> [新增] -> [專案]
        - 在搜尋方塊中輸入 `Q#`
        - 選取 [Q# 應用程式]
        - 選取 [**下一步**]
        - 選擇應用程式的名稱和位置
        - 選取 [建立]

    - 檢查專案

        您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。

    - 執行應用程式

        - 選取 [偵錯] -> [啟動但不偵錯]
        - 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> * 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  

## 使用 Visual Studio Code 的 Q # C# + 進行開發<a name="VSC"></a>

Visual Studio Code （VS Code）提供豐富的環境，供您在 Windows、Linux 和 Mac 上開發 Q # 程式。  Q # VS Code 延伸模組包含 Q # 語法反白顯示、程式碼完成和 Q # 程式碼片段的支援。

1. 必要條件

   - [VS 程式碼](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

1. 安裝 Quantum VS Code 擴充功能

    - 安裝 [VS Code 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. 安裝 Quantum 專案範本：

   - 移至 [檢視] -> [命令選擇區]
   - 選取 [ **Q #：安裝專案範本**]

    您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立新專案：

        - 移至 [檢視] -> [命令選擇區]
        - 選取 [ **Q #：建立新專案**]
        - 選取**獨立主控台應用程式**
        - 瀏覽至您要建立應用程式的檔案系統位置
        - 專案建立好之後，請按一下 [開啟新專案...] 按鈕

    - 如果您還沒有安裝 VS Code C#的延伸模組，將會顯示快顯視窗。 安裝延伸模組。 

    - 執行應用程式：

        - 移至**終端**機 -> **新的終端**機
        - 輸入 `dotnet run`
        - 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`


> [!NOTE]
> * Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## 使用 `dotnet` 命令列工具C#搭配 Q # + 進行開發<a name="command"></a>

當然，您也可以從命令列建置並執行 Q# 程式，只要安裝 .NET Core SDK 和 QDK 專案範本即可。 

1. 必要條件

    - [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

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

    
## <a name="whats-next"></a>接下來呢？

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。
