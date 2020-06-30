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
# <a name="develop-with-q-and-net"></a><span data-ttu-id="c1192-102">使用 Q# 和 .NET 進行開發</span><span class="sxs-lookup"><span data-stu-id="c1192-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="c1192-103">Q# 的建置目的是為了能夠與如 C# 和 F# 等 .NET 語法充分配合。</span><span class="sxs-lookup"><span data-stu-id="c1192-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="c1192-104">在本指南中，我們會示範如何將 Q # 搭配以 .NET 語言撰寫的主機程式使用。</span><span class="sxs-lookup"><span data-stu-id="c1192-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1192-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="c1192-105">Prerequisites</span></span>

- <span data-ttu-id="c1192-106">安裝 Quantum Development Kit [以搭配 Q# 命令列專案使用](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="c1192-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="c1192-107">建立 Q# 程式庫與 .NET 主機</span><span class="sxs-lookup"><span data-stu-id="c1192-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="c1192-108">第一個步驟是為您的 Q # 程式庫建立專案，及為將呼叫 Q # 程式庫中所定義作業和函式的 .NET 主機建立專案。</span><span class="sxs-lookup"><span data-stu-id="c1192-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="c1192-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c1192-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="c1192-110">建立新 Q# 程式庫</span><span class="sxs-lookup"><span data-stu-id="c1192-110">Create a new Q# library</span></span>
  - <span data-ttu-id="c1192-111">移至 [檔案] -> [新增] -> [專案]</span><span class="sxs-lookup"><span data-stu-id="c1192-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="c1192-112">在搜尋方塊中鍵入 "Q#"。</span><span class="sxs-lookup"><span data-stu-id="c1192-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="c1192-113">選取 [Q# 程式庫]</span><span class="sxs-lookup"><span data-stu-id="c1192-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="c1192-114">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="c1192-114">Select **Next**</span></span>
  - <span data-ttu-id="c1192-115">選擇程式庫的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="c1192-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="c1192-116">請確定 [將專案和解決方案放在相同目錄中] 為**未勾選**</span><span class="sxs-lookup"><span data-stu-id="c1192-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="c1192-117">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="c1192-117">Select **Create**</span></span>
- <span data-ttu-id="c1192-118">建立新的 C# 或 F# 主機程式</span><span class="sxs-lookup"><span data-stu-id="c1192-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="c1192-119">移至 [檔案] → [新增] → [專案]</span><span class="sxs-lookup"><span data-stu-id="c1192-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="c1192-120">為 C# 或 F# 選取 \[主控台應用程式 \(.NET Core\)\]</span><span class="sxs-lookup"><span data-stu-id="c1192-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="c1192-121">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="c1192-121">Select **Next**</span></span>
  - <span data-ttu-id="c1192-122">在 [解決方案] 下方，選取 [新增至解決方案]</span><span class="sxs-lookup"><span data-stu-id="c1192-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="c1192-123">選擇主機程式的名稱</span><span class="sxs-lookup"><span data-stu-id="c1192-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="c1192-124">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="c1192-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="c1192-125">Visual Studio Code 或命令列</span><span class="sxs-lookup"><span data-stu-id="c1192-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="c1192-126">建立新 Q# 程式庫</span><span class="sxs-lookup"><span data-stu-id="c1192-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="c1192-127">建立新的 C# 或 F# 主控台專案</span><span class="sxs-lookup"><span data-stu-id="c1192-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="c1192-128">從主機程式新增您的 Q# 程式庫作為參考</span><span class="sxs-lookup"><span data-stu-id="c1192-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="c1192-129">[選擇性] 為這兩個專案建立解決方案</span><span class="sxs-lookup"><span data-stu-id="c1192-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="c1192-130">從 .NET 呼叫 Q #</span><span class="sxs-lookup"><span data-stu-id="c1192-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="c1192-131">依照上述指示設定好專案後，您便可以從 .NET 主控台應用程式呼叫 Q #。</span><span class="sxs-lookup"><span data-stu-id="c1192-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="c1192-132">Q # 編譯器會針對每個 Q # 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行配量程式。</span><span class="sxs-lookup"><span data-stu-id="c1192-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="c1192-133">例如，[.NET 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含 Q# 作業的下列範例：</span><span class="sxs-lookup"><span data-stu-id="c1192-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="c1192-134">若要在配量模擬器上從 .NET 呼叫此作業，您可以使用 Q # 編譯器所產生 `RunAlgorithm` .NET 類別的 `Run`方法：</span><span class="sxs-lookup"><span data-stu-id="c1192-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="c1192-135">C#</span><span class="sxs-lookup"><span data-stu-id="c1192-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="c1192-136">F#</span><span class="sxs-lookup"><span data-stu-id="c1192-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="c1192-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c1192-137">Next steps</span></span>

<span data-ttu-id="c1192-138">您已經為 Q # 命令列程式及與 .NET 的互通性設定了 Quantum Development Kit，現在您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="c1192-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
