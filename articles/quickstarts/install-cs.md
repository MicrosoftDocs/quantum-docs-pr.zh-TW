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
ms.openlocfilehash: 24318380e0e63957a51961762a33446fe0121b21
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863681"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="13c97-102">使用 Q# 和 .NET 進行開發</span><span class="sxs-lookup"><span data-stu-id="13c97-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="13c97-103">Q# 的建置目的是為了能夠與如 C# 和 F# 等 .NET 語法充分配合。</span><span class="sxs-lookup"><span data-stu-id="13c97-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="13c97-104">在本指南中，我們將示範如何搭配使用 Q# 與以 .NET 語言撰寫的主機程式。</span><span class="sxs-lookup"><span data-stu-id="13c97-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="13c97-105">首先，我們會建立 Q# 應用程式和 .NET 主機，然後示範如何從主機呼叫 Q#。</span><span class="sxs-lookup"><span data-stu-id="13c97-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13c97-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="13c97-106">Prerequisites</span></span>

- <span data-ttu-id="13c97-107">安裝 Quantum 開發套件以[與 Q#專案](xref:microsoft.quantum.install.standalone)搭配使用。</span><span class="sxs-lookup"><span data-stu-id="13c97-107">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="13c97-108">建立 Q# 程式庫和 .NET 主機</span><span class="sxs-lookup"><span data-stu-id="13c97-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="13c97-109">第一個步驟是為您的 Q# 程式庫建立專案，以及為即將呼叫 Q# 程式庫中定義之作業和函式的 .NET 主機建立專案。</span><span class="sxs-lookup"><span data-stu-id="13c97-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="13c97-110">依照對應至您開發環境的索引標籤中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="13c97-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="13c97-111">如果您使用 Visual Studio 或 VS Code 以外的編輯器，只要遵循命令提示字元步驟即可。</span><span class="sxs-lookup"><span data-stu-id="13c97-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="13c97-112">Visual Studio Code 或命令提示字元</span><span class="sxs-lookup"><span data-stu-id="13c97-112">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="13c97-113">建立新的 Q# 程式庫</span><span class="sxs-lookup"><span data-stu-id="13c97-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="13c97-114">建立新的 C# 或 F# 主控台專案</span><span class="sxs-lookup"><span data-stu-id="13c97-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="13c97-115">從主機程式新增您的 Q# 程式庫作為參考</span><span class="sxs-lookup"><span data-stu-id="13c97-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="13c97-116">[選擇性] 為這兩個專案建立解決方案</span><span class="sxs-lookup"><span data-stu-id="13c97-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="13c97-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="13c97-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="13c97-118">建立新的 Q# 程式庫</span><span class="sxs-lookup"><span data-stu-id="13c97-118">Create a new Q# library</span></span>
  - <span data-ttu-id="13c97-119">移至 [檔案] -> [新增] -> [專案]</span><span class="sxs-lookup"><span data-stu-id="13c97-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="13c97-120">在搜尋方塊中鍵入 "Q#"</span><span class="sxs-lookup"><span data-stu-id="13c97-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="13c97-121">選取 [Q# 程式庫]</span><span class="sxs-lookup"><span data-stu-id="13c97-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="13c97-122">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="13c97-122">Select **Next**</span></span>
  - <span data-ttu-id="13c97-123">選擇程式庫的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="13c97-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="13c97-124">請確定 [將專案和解決方案放在相同目錄中] 為**未勾選**</span><span class="sxs-lookup"><span data-stu-id="13c97-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="13c97-125">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="13c97-125">Select **Create**</span></span>
- <span data-ttu-id="13c97-126">建立新的 C# 或 F# 主機程式</span><span class="sxs-lookup"><span data-stu-id="13c97-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="13c97-127">移至 [檔案] → [新增] → [專案]</span><span class="sxs-lookup"><span data-stu-id="13c97-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="13c97-128">為 C# 或 F# 選取 \[主控台應用程式 \(.NET Core\)\]</span><span class="sxs-lookup"><span data-stu-id="13c97-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="13c97-129">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="13c97-129">Select **Next**</span></span>
  - <span data-ttu-id="13c97-130">在 [解決方案] 下方，選取 [新增至解決方案]</span><span class="sxs-lookup"><span data-stu-id="13c97-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="13c97-131">選擇主機程式的名稱</span><span class="sxs-lookup"><span data-stu-id="13c97-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="13c97-132">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="13c97-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="13c97-133">從 .NET 呼叫 Q#</span><span class="sxs-lookup"><span data-stu-id="13c97-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="13c97-134">依照上述指示設定好專案後，您便可以從 .NET 主控台應用程式呼叫 Q#。</span><span class="sxs-lookup"><span data-stu-id="13c97-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="13c97-135">Q# 編譯器會針對每個 Q# 作業和函式建立 .NET 類別，讓您能夠在模擬器上執行配量程式。</span><span class="sxs-lookup"><span data-stu-id="13c97-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="13c97-136">例如，[.NET 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含 Q# 作業的下列範例：</span><span class="sxs-lookup"><span data-stu-id="13c97-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="13c97-137">若要在配量模擬器上從 .NET 呼叫此作業，您可以使用 Q# 編譯器所產生之 `RunAlgorithm` .NET 類別的 `Run` 方法：</span><span class="sxs-lookup"><span data-stu-id="13c97-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="13c97-138">C#</span><span class="sxs-lookup"><span data-stu-id="13c97-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="13c97-139">F#</span><span class="sxs-lookup"><span data-stu-id="13c97-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="13c97-140">後續步驟</span><span class="sxs-lookup"><span data-stu-id="13c97-140">Next steps</span></span>

<span data-ttu-id="13c97-141">您已經為 Q# 應用程式和與 .NET 的互通性設定了 Quantum 開發套件，現在您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="13c97-141">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
