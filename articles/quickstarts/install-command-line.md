---
title: 以 Q# 命令列應用程式開發
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871428"
---
# <a name="develop-with-q-command-line-applications"></a>以 Q# 命令列應用程式開發

Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。

## <a name="prerequisites"></a>必要條件

- [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安裝

雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但建議使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 來在本機開發您的 Q # 應用程式。 若要透過網頁瀏覽器在雲端中進行開發，建議使用 Visual Studio Codespaces。 在這些環境中進行的開發將包含 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。 

若要設定 VS Code：

1. 下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。
2. 安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

若要設定 Visual Studio：

1. 下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。
2. 下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。

設定 Visual Studio Codespaces：

1. 建立 [Azure 帳戶](https://azure.microsoft.com/free/)。
2. 建立 Codespaces 環境。 遵循[快速入門](https://docs.microsoft.com/visualstudio/online/quickstarts/browser)。 建立 Codespace 時，建議您在 [Git 存放庫] 欄位中輸入 `microsoft/Quantum`，以載入 QDK 特定的設定。
3. 您現在可以啟動新的環境，並透過 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)，在瀏覽器中開始進行開發。 或者，您也可以使用本機安裝的 VS Code，並使用 Codespaces 做為[遠端環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。


若要為其他環境安裝 QDK，請在命令列中輸入：

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>使用 Q# 進行開發

遵循與您的環境對應的索引標籤中的指示。

### <a name="vs-code"></a>[VS 程式碼](#tab/tabid-vscode)

若要建立新專案：

1. 按一下 [檢視] -> [命令選擇區]，然後選取 [Q#:**建立新專案]** 。
2. 按一下 [獨立主控台應用程式]。
3. 瀏覽至要儲存專案的位置，然後按一下 [建立專案]。
4. 成功建立專案後，按一下右下方的 [開啟新增專案...]。
        
檢查專案。 您應該會看到名為 `Program.qs` 的原始程式檔，這個 Q # 程式定義一個可將訊息列印至主控台的簡單作業。

若要執行應用程式：
1. 按一下 [終端機] -> [新增終端機]。
2. 在終端機提示中，輸入 `dotnet run`。
3. 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`


> [!NOTE]
> VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

透過建立 Q # `Hello World` 應用程式來確認您的 Visual Studio 安裝。

若要建立新的 C# 應用程式：
1. 開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。
2. 在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按一下 [下一步]。
3. 為應用程式輸入名稱和位置，然後按一下 [建立]。


檢查專案。 您應該會看到名為 `Program.qs` 的原始程式檔，這個 Q # 程式定義一個可將訊息列印至主控台的簡單作業。

若要執行應用程式：
1. 選取 [偵錯] -> [啟動但不偵錯]。
2. 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  

### <a name="other-editors-with-the-command-line"></a>[其他有命令列的編輯器](#tab/tabid-cmdline)

透過建立 Q# `Hello World` 應用程式來確認您的安裝。

1. 安裝專案範本。

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 建立新的應用程式：
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. 瀏覽至新的應用程式目錄：
    ```dotnetcli
    cd runSayHello
    ```

    此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式定義一個可將訊息列印至主控台的簡單作業。 您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。 

1. 執行程式：
    ```dotnetcli
    dotnet run
    ```

1. 您應該會看到列印出下列文字：`Hello quantum world!`

***

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
