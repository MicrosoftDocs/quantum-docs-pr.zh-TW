---
title: 以 Q# 命令列應用程式開發
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274066"
---
# <a name="develop-with-q-command-line-applications"></a>以 Q# 命令列應用程式開發

Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。

## <a name="prerequisites"></a>必要條件

- [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安裝

雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但建議您為 Q # 應用程式使用 Visual Studio Code (VS Code) 或 Visual Studio IDE。 使用這些工具進行開發，可讓您存取豐富的功能。

若要設定 VS Code：

1. 下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。
2. 安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

若要設定 Visual Studio：

1. 下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。
2. 下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。


## <a name="develop-with-q-using-vs-code"></a>透過 VS Code，使用 Q# 來開發

安裝 Q# 專案範本：

1. 開啟 VS Code。
2. 按一下 [檢視] -> [命令選擇區]。
3. 選取 [Q#:安裝專案範本]。

當顯示 [已成功專案範本] 時，QDK 已準備好搭配您自己的應用程式與程式庫使用。

若要建立新專案：

1. 按一下 [檢視] -> [命令選擇區]，然後選取 [Q#:**建立新專案]** 。
2. 按一下 [獨立主控台應用程式]。
3. 瀏覽至要儲存專案的位置，然後按一下 [建立專案]。
4. 成功建立專案後，按一下右下方的 [開啟新增專案...]。
        
檢查專案。 您應該會看到名為 `Program.qs` 的原始程式檔，這是一個 Q # 程式，可定義將訊息列印至主控台的簡單作業。

若要執行應用程式：
1. 按一下 [終端機] -> [新增終端機]。
2. 在終端機提示中，輸入 `dotnet run`。
3. 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`


> [!NOTE]
> VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## <a name="develop-with-q-using-visual-studio"></a>使用 Visual Studio，透過 Q# 開發

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


## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
