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
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="73590-102">搭配 C\#和 F 使用 Q #\#</span><span class="sxs-lookup"><span data-stu-id="73590-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="73590-103">問 # 的設計可與 .NET 語言（例如 c # 和 F #）搭配運作。</span><span class="sxs-lookup"><span data-stu-id="73590-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="73590-104">在本指南中，我們將示範如何搭配以 .NET 語言撰寫的主機程式來使用 Q #。</span><span class="sxs-lookup"><span data-stu-id="73590-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73590-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="73590-105">Prerequisites</span></span>

- <span data-ttu-id="73590-106">安裝[用於 Q # 命令列專案](xref:microsoft.quantum.install.standalone)的量子開發工具組。</span><span class="sxs-lookup"><span data-stu-id="73590-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="73590-107">建立 Q # 程式庫和 .NET 主機</span><span class="sxs-lookup"><span data-stu-id="73590-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="73590-108">第一個步驟是為您的 Q # 程式庫建立專案，以及針對將呼叫您的 Q # 程式庫中所定義之作業和函式的 .NET 主機。</span><span class="sxs-lookup"><span data-stu-id="73590-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="73590-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="73590-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="73590-110">建立新的 Q # 程式庫</span><span class="sxs-lookup"><span data-stu-id="73590-110">Create a new Q# library</span></span>
  - <span data-ttu-id="73590-111">移至**File** -> [檔案] [**新增** -> **專案**]</span><span class="sxs-lookup"><span data-stu-id="73590-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="73590-112">在搜尋方塊中輸入 "Q #"</span><span class="sxs-lookup"><span data-stu-id="73590-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="73590-113">選取 [ **Q # 程式庫**]</span><span class="sxs-lookup"><span data-stu-id="73590-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="73590-114">選取**下一步**</span><span class="sxs-lookup"><span data-stu-id="73590-114">Select **Next**</span></span>
  - <span data-ttu-id="73590-115">選擇程式庫的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="73590-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="73590-116">請**確定未核**取 [將專案和方案放在相同的目錄]</span><span class="sxs-lookup"><span data-stu-id="73590-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="73590-117">選取 [**建立**]</span><span class="sxs-lookup"><span data-stu-id="73590-117">Select **Create**</span></span>
- <span data-ttu-id="73590-118">建立新的 c # 或 F # 主機程式</span><span class="sxs-lookup"><span data-stu-id="73590-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="73590-119">前往 [檔案 **] → [** **新增**] → [**專案**]</span><span class="sxs-lookup"><span data-stu-id="73590-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="73590-120">針對 c # 或 F 選取 [主控台應用程式（.NET Core）]#</span><span class="sxs-lookup"><span data-stu-id="73590-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="73590-121">選取**下一步**</span><span class="sxs-lookup"><span data-stu-id="73590-121">Select **Next**</span></span>
  - <span data-ttu-id="73590-122">在 [*方案*] 底下，選取 [新增至解決方案]</span><span class="sxs-lookup"><span data-stu-id="73590-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="73590-123">選擇主機程式的名稱</span><span class="sxs-lookup"><span data-stu-id="73590-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="73590-124">選取 [**建立**]</span><span class="sxs-lookup"><span data-stu-id="73590-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="73590-125">Visual Studio Code 或命令列</span><span class="sxs-lookup"><span data-stu-id="73590-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="73590-126">建立新的 Q # 程式庫</span><span class="sxs-lookup"><span data-stu-id="73590-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="73590-127">建立新的 c # 或 F # 主控台專案</span><span class="sxs-lookup"><span data-stu-id="73590-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="73590-128">新增您的 Q # 程式庫做為主機程式的參考</span><span class="sxs-lookup"><span data-stu-id="73590-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="73590-129">選擇性建立這兩個專案的方案</span><span class="sxs-lookup"><span data-stu-id="73590-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="73590-130">從 .NET 呼叫 Q #</span><span class="sxs-lookup"><span data-stu-id="73590-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="73590-131">依照上述指示設定專案之後，您可以從 .NET 主控台應用程式呼叫 Q #。</span><span class="sxs-lookup"><span data-stu-id="73590-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="73590-132">Q # 編譯器會針對每個 Q # 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行您的量副程式。</span><span class="sxs-lookup"><span data-stu-id="73590-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="73590-133">例如， [.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含下列 Q # 作業的範例：</span><span class="sxs-lookup"><span data-stu-id="73590-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="73590-134">若要從 .NET 在配量模擬器上呼叫這項作業，您`Run`可以使用由`RunAlgorithm` Q # 編譯器所產生之 .net 類別的方法：</span><span class="sxs-lookup"><span data-stu-id="73590-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="73590-135">C#</span><span class="sxs-lookup"><span data-stu-id="73590-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="73590-136">F#</span><span class="sxs-lookup"><span data-stu-id="73590-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="73590-137">下一步</span><span class="sxs-lookup"><span data-stu-id="73590-137">What's next?</span></span>

<span data-ttu-id="73590-138">現在您已設定了適用于 Q # 命令列程式的配量開發工具組，而且為了與 .NET 互通，您可以撰寫並執行[您的第一個量副程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="73590-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
