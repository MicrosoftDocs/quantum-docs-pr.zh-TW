---
title: 在 IDE 中使用 Q# 應用程式進行開發
description: 了解如何建立從命令提示字元執行的 Q# 應用程式。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844326"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>在 IDE 中使用 Q# 應用程式進行開發

Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。 您可以在 Visual Studio Code (VS Code)、Visual Studio、Visual Studio Codespaces 中開發 Q# 應用程式，或使用任何編輯器/IDE，以及從 .NET 主控台執行應用程式。 

## <a name="prerequisites-for-all-environments"></a>所有環境的必要條件

- [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安裝

雖然您可以在任何 IDE 中建立 Q# 應用程式，但建議使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本機開發您的 Q# 應用程式。 若要透過網頁瀏覽器在雲端中進行開發，建議使用 Visual Studio Codespaces。 在這些環境中進行的開發將利用 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。 

### <a name="to-configure-for-vs-code"></a>若要為 VS Code 設定：

1. 下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。
2. 安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

### <a name="to-configure-for-visual-studio"></a>若要為 Visual Studio 設定：

1. 下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。
2. 下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。

### <a name="to-configure-for-another-environment"></a>若要為另一個環境設定： 

1. 在命令提示字元中，輸入以下：

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>若要為 Visual Studio Codespaces 設定：

1. 建立 [Azure 帳戶](https://azure.microsoft.com/free/)。
2. 建立 Codespaces 環境。 遵循[快速入門](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)。 建立 Codespace 時，建議您在 [Git 存放庫] 欄位中輸入 `microsoft/Quantum`，以載入 QDK 特定的設定。
3. 您現在可以啟動新的環境，並透過 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)，在瀏覽器中開始進行開發。 或者，您也可以使用本機安裝的 VS Code，並使用 Codespaces 做為[遠端環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。

## <a name="develop-with-no-locq"></a>使用 Q# 進行開發

依照對應至您開發環境索引標籤上的指示進行。

### <a name="vs-code"></a>[VS 程式碼](#tab/tabid-vscode)

若要建立新專案：

1. 按一下 [檢視] -> [命令選擇區]，然後選取 **[Q#：建立新專案]** 。
2. 按一下 [獨立主控台應用程式]。
3. 瀏覽至要儲存專案的位置。 輸入專案名稱，並按一下 [建立專案]。
4. 成功建立專案後，按一下右下方的 [開啟新增專案...]。

檢查專案。 您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。

若要執行應用程式：

1. 按一下 [終端機] -> [新增終端機]。
2. 在終端機提示中，輸入 `dotnet run`。
3. 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`

> [!NOTE]
> VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

藉由建立 Q# `Hello World` 應用程式來確認您的 Visual Studio 安裝。

若要建立新的 Q# 應用程式：

1. 開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。
2. 在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按 [下一步]。
3. 為應用程式輸入名稱和位置，然後按一下 [建立]。


檢查專案。 您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。

若要執行應用程式：

1. 選取 [偵錯] -> [啟動但不偵錯]。
2. 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  

### <a name="other-editors-with-the-command-prompt"></a>[其他有命令提示字元的編輯器](#tab/tabid-cmdline)

藉由建立 Q# `Hello World` 應用程式來確認您的安裝。

1. 建立新的應用程式：

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. 瀏覽至新的應用程式目錄：

    ```dotnetcli
    cd runSayHello
    ```

    此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。 您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。 

1. 執行程式：

    ```dotnetcli
    dotnet run
    ```

1. 您應該會看到列印出下列文字：`Hello quantum world!`

***

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
