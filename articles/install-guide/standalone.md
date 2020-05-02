---
title: '執行沒有驅動程式和主機語言的 Q # 程式'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706796"
---
# <a name="q-command-line-applications"></a>Q # 命令列應用程式

問 # 程式可以自己執行，而不需要像 c #、F # 或 Python 等主機語言的驅動程式。

## <a name="pre-requisites"></a>必要條件

- [.NET Core SDK 3.1 或更新版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安裝

雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但我們強烈建議您針對您的 Q # 應用程式使用 Visual Studio Code （VS Code）或 Visual Studio IDE。 藉由使用 VS Code 或 Visual Studio 和 QDK Visual Studio Code 延伸模組，您可以存取更豐富的功能。

- 安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）
- 安裝[適用于 VS Code 或的 QDK 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)功能
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載
- 下載並安裝[Visual Studio 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)功能


## <a name="develop-with-q-using-vs-code"></a>使用 Q # 進行開發 VS Code

安裝 Quantum 專案範本：

- 移至**View** -> **命令**選擇區
- 選取 [ **Q #：安裝專案範本**]

您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。
- 建立新專案：
  - 移至**View** -> **命令**選擇區
  - 選取 [ **Q #：建立新專案**]
  - 選取**獨立主控台應用程式**
  - 瀏覽至您要建立應用程式的檔案系統位置
  - 專案建立好之後，請按一下 [開啟新專案...]**** 按鈕
        
- 檢查專案
  - 您應該會看到名`Program.qs`為 [已建立] 的檔案，這是一個 Q # 程式，可定義簡單的作業，以將訊息列印至主控台。

- 執行應用程式：
  - 移至**終端** -> 機**新終端**機
  - 輸入 `dotnet run`
  - 您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`


> [!NOTE]
> * Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。 如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。

## <a name="develop-with-q-using-visual-studio"></a>使用 Q # 進行開發 Visual Studio

建立 `Hello World` 應用程式來驗證安裝

- 建立新的 C# 應用程式
  - 移至**File** -> [檔案] [**新增** -> **專案**]
  - 在搜尋方塊中輸入 `Q#`
  - 選取 [Q# 應用程式]****
  - 選取**下一步**
  - 選擇應用程式的名稱和位置
  - 選取 [**建立**]

- 檢查專案
  - 您應該會看到名`Program.qs`為的檔案已建立，這是一個 Q # 程式，定義將訊息列印至主控台的簡單操作。

- 執行應用程式
  - 選取 [不進行調試的**Debug** -> **啟動**]
  - 您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。

> [!NOTE]
> * 如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  


## <a name="whats-next"></a>下一步

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。
