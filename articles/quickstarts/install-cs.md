---
title: 使用 Q# 和 .NET 進行開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274030"
---
# <a name="develop-with-q-and-net"></a>使用 Q# 和 .NET 進行開發

Q# 的建置目的是為了能夠與如 C# 和 F# 等 .NET 語法充分配合。
在本指南中，我們會示範如何將 Q # 搭配以 .NET 語言撰寫的主機程式使用。

## <a name="prerequisites"></a>必要條件

- 安裝 Quantum Development Kit [以搭配 Q# 命令列專案使用](xref:microsoft.quantum.install.standalone)。

## <a name="creating-a-q-library-and-a-net-host"></a>建立 Q# 程式庫與 .NET 主機

第一個步驟是為您的 Q # 程式庫建立專案，及為將呼叫 Q # 程式庫中所定義作業和函式的 .NET 主機建立專案。

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 建立新 Q# 程式庫
  - 移至 [檔案] -> [新增] -> [專案]
  - 在搜尋方塊中鍵入 "Q#"。
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

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code 或命令列](#tab/tabid-cmdline)

- 建立新 Q# 程式庫

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

***

## <a name="calling-into-q-from-net"></a>從 .NET 呼叫 Q #

依照上述指示設定好專案後，您便可以從 .NET 主控台應用程式呼叫 Q #。
Q # 編譯器會針對每個 Q # 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行配量程式。

例如，[.NET 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含 Q# 作業的下列範例：

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

若要在配量模擬器上從 .NET 呼叫此作業，您可以使用 Q # 編譯器所產生 `RunAlgorithm` .NET 類別的 `Run`方法：

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>後續步驟

您已經為 Q # 命令列程式及與 .NET 的互通性設定了 Quantum Development Kit，現在您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。
