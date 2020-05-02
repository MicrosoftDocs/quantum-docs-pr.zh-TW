---
title: 使用 Q# + C# 來開發
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680171"
---
# <a name="using-q-with-c-and-f"></a>搭配 C\#和 F 使用 Q #\#

問 # 的設計可與 .NET 語言（例如 c # 和 F #）搭配運作。
在本指南中，我們將示範如何搭配以 .NET 語言撰寫的主機程式來使用 Q #。

## <a name="prerequisites"></a>Prerequisites

- 安裝[用於 Q # 命令列專案](xref:microsoft.quantum.install.standalone)的量子開發工具組。

## <a name="creating-a-q-library-and-a-net-host"></a>建立 Q # 程式庫和 .NET 主機

第一個步驟是為您的 Q # 程式庫建立專案，以及針對將呼叫您的 Q # 程式庫中所定義之作業和函式的 .NET 主機。

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 建立新的 Q # 程式庫
  - 移至**File** -> [檔案] [**新增** -> **專案**]
  - 在搜尋方塊中輸入 "Q #"
  - 選取 [ **Q # 程式庫**]
  - 選取**下一步**
  - 選擇程式庫的名稱和位置
  - 請**確定未核**取 [將專案和方案放在相同的目錄]
  - 選取 [**建立**]
- 建立新的 c # 或 F # 主機程式
  - 前往 [檔案 **] → [** **新增**] → [**專案**]
  - 針對 c # 或 F 選取 [主控台應用程式（.NET Core）]#
  - 選取**下一步**
  - 在 [*方案*] 底下，選取 [新增至解決方案]
  - 選擇主機程式的名稱
  - 選取 [**建立**]

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code 或命令列](#tab/tabid-cmdline)

- 建立新的 Q # 程式庫

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 建立新的 c # 或 F # 主控台專案

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- 新增您的 Q # 程式庫做為主機程式的參考

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- 選擇性建立這兩個專案的方案

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>從 .NET 呼叫 Q #

依照上述指示設定專案之後，您可以從 .NET 主控台應用程式呼叫 Q #。
Q # 編譯器會針對每個 Q # 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行您的量副程式。

例如， [.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含下列 Q # 作業的範例：

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

若要從 .NET 在配量模擬器上呼叫這項作業，您`Run`可以使用由`RunAlgorithm` Q # 編譯器所產生之 .net 類別的方法：

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>下一步

現在您已設定了適用于 Q # 命令列程式的配量開發工具組，而且為了與 .NET 互通，您可以撰寫並執行[您的第一個量副程式](xref:microsoft.quantum.write-program)。
