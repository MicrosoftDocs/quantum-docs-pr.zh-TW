---
title: 使用 Q# 和 .NET 進行開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 96a1d0d75f3ff7de11407fd76479cbae86ce7571
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759267"
---
# <a name="develop-with-no-locq-and-net"></a>使用 Q# 和 .NET 進行開發

Q# 的建置目的是為了能夠與如 C# 和 F# 等 .NET 語法充分配合。
在本指南中，我們將示範如何搭配使用 Q# 與以 .NET 語言撰寫的主機程式。

首先，我們會建立 Q# 應用程式和 .NET 主機，然後示範如何從主機呼叫 Q#。

## <a name="prerequisites"></a>必要條件

- 安裝 Quantum 開發套件以[與 Q#專案](xref:microsoft.quantum.install.standalone)搭配使用。

## <a name="creating-a-no-locq-library-and-a-net-host"></a>建立 Q# 程式庫和 .NET 主機

第一個步驟是為您的 Q# 程式庫建立專案，以及為即將呼叫 Q# 程式庫中定義之作業和函式的 .NET 主機建立專案。

依照對應至您開發環境的索引標籤中的指示進行。
如果您使用 Visual Studio 或 VS Code 以外的編輯器，只要遵循命令提示字元步驟即可。

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code 或命令提示字元](#tab/tabid-cmdline)

- 建立新的 Q# 程式庫

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 建立新的 C# 或 F# 主控台專案

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- 從主機程式新增您的 Q# 程式庫作為參考

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [選擇性] 為這兩個專案建立解決方案

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 建立新的 Q# 程式庫
  - 移至 [檔案] -> [新增] -> [專案]
  - 在搜尋方塊中鍵入 "Q#"
  - 選取 [Q# 程式庫]
  - 選取 [**下一步**]
  - 選擇程式庫的名稱和位置
  - 請確定 [將專案和解決方案放在相同目錄中] 為**未勾選**
  - 選取 [建立] 
- 建立新的 C# 或 F# 主機程式
  - 移至 [檔案] → [新增] → [專案]
  - 為 C# 或 F# 選取 \[主控台應用程式 \(.NET Core\)\]
  - 選取 [**下一步**]
  - 在 [解決方案] 下方，選取 [新增至解決方案]
  - 選擇主機程式的名稱
  - 選取 [建立] 

***

## <a name="calling-into-no-locq-from-net"></a>從 .NET 呼叫 Q#

依照上述指示設定好專案後，您便可以從 .NET 主控台應用程式呼叫 Q#。
Q# 編譯器會針對每個 Q# 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行配量程式。

例如，[.NET 互通性範例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)包含 Q# 作業的下列範例：

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

若要在配量模擬器上從 .NET 呼叫此作業，您可以使用 Q# 編譯器所產生之 `RunAlgorithm` .NET 類別的 `Run` 方法：

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>後續步驟

您已經為 Q# 應用程式和與 .NET 的互通性設定了 Quantum 開發套件，現在您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。
