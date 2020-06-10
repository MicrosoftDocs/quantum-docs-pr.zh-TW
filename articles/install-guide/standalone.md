---
title: '使用 Q # 命令列應用程式進行開發'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630265"
---
# <a name="develop-with-q-command-line-applications"></a>使用 Q # 命令列應用程式進行開發

問 # 程式可以自己執行，而不需要像 c #、F # 或 Python 等主機語言的驅動程式。

## <a name="prerequisites"></a>必要條件

- [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安裝

雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但我們建議您為您的 Q # 應用程式使用 Visual Studio Code （VS Code）或 Visual Studio IDE。 在這些工具中進行開發，可讓您存取豐富的功能。

若要設定 VS Code：

1. 下載並安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）。
2. 安裝[適用于 VS Code 的 MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

若要設定 Visual Studio：

1. 下載並安裝[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並啟用 .net Core 跨平臺開發工作負載。
2. 下載並安裝[MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。


## <a name="develop-with-q-using-vs-code"></a>使用 Q # 進行開發 VS Code

安裝 Q # 專案範本：

1. 開啟 VS Code。
2. 按一下 [ **View**  ->  **Command 調色板**]。
3. 選取 [ **Q #：安裝專案範本**]。

**成功安裝專案範本**時，QDK 就可以與您自己的應用程式和程式庫搭配使用。

若要建立新的專案：

1. 按一下 [**視圖**] [命令選擇區]  ->  **Command Palette** ，然後選取 [ **Q #：建立新專案**]。
2. 按一下 [**獨立主控台應用程式**]。
3. 流覽至要儲存專案的位置，然後按一下 [**建立專案**]。
4. 成功建立專案後，按一下右下方的 [**開啟新專案**]。
        
檢查項目。 您應該會看到名為的原始 `Program.qs` 程式檔，這是定義簡單作業以將訊息列印至主控台的 Q # 程式。

若要執行應用程式：
1. 按一下 [**終端**機] [  ->  **新終端**機]。
2. 在終端機提示中，輸入 `dotnet run` 。
3. 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`


> [!NOTE]
> VS Code Q # 延伸模組目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## <a name="develop-with-q-using-visual-studio"></a>使用 Q # 進行開發 Visual Studio

藉由建立 Q # 應用程式來驗證您的 Visual Studio 安裝 `Hello World` 。

若要建立新的 Q # 應用程式：
1. 開啟 Visual Studio，然後**按一下 [** 檔案] [新增] [  ->  **New**  ->  **專案**]。
2. `Q#`在搜尋方塊中輸入，選取 [ **Q # 應用程式**]，然後按 **[下一步]**。
3. 輸入應用程式的 [名稱] 和 [位置]，然後按一下 [**建立**]。


檢查項目。 您應該會看到名為的原始 `Program.qs` 程式檔，這是定義簡單作業以將訊息列印至主控台的 Q # 程式。

若要執行應用程式：
1. 選取 **[** 在  ->  **不進行調試的情況下啟動**]。
2. 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> 如果您在一個 Visual Studio 方案中有多個專案，則方案中包含的所有專案都必須位於方案所在的相同資料夾中，或是在其中一個子資料夾中。  


## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
