---
title: 使用其他連結 Q# 庫
description: 瞭解如何將其他連結 Q# 庫新增至您的量子應用程式。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869574"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="bd077-103">使用其他連結 Q# 庫</span><span class="sxs-lookup"><span data-stu-id="bd077-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="bd077-104">量子開發工具組透過可新增至專案的_NuGet 套件_，提供額外的網域特定功能 Q# 。</span><span class="sxs-lookup"><span data-stu-id="bd077-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="bd077-105">Q#機庫</span><span class="sxs-lookup"><span data-stu-id="bd077-105">Q# Library</span></span>  | <span data-ttu-id="bd077-106">Nuget 套件</span><span class="sxs-lookup"><span data-stu-id="bd077-106">NuGet package</span></span> | <span data-ttu-id="bd077-107">注意</span><span class="sxs-lookup"><span data-stu-id="bd077-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="bd077-108">Q#標準程式庫</span><span class="sxs-lookup"><span data-stu-id="bd077-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="bd077-109">**Microsoft 量子標準**</span><span class="sxs-lookup"><span data-stu-id="bd077-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="bd077-110">預設包含</span><span class="sxs-lookup"><span data-stu-id="bd077-110">Included by default</span></span> |
| [<span data-ttu-id="bd077-111">量子化學程式庫</span><span class="sxs-lookup"><span data-stu-id="bd077-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="bd077-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="bd077-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="bd077-113">量子數值程式庫</span><span class="sxs-lookup"><span data-stu-id="bd077-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="bd077-114">**Microsoft 量子. 數值**</span><span class="sxs-lookup"><span data-stu-id="bd077-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="bd077-115">量子機器學習程式庫</span><span class="sxs-lookup"><span data-stu-id="bd077-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="bd077-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="bd077-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="bd077-117">安裝配量開發工具組以搭配慣用的環境和主機語言使用之後，您就可以輕鬆地將程式庫新增至個別 Q# 專案，而不需要進行任何進一步的安裝。</span><span class="sxs-lookup"><span data-stu-id="bd077-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="bd077-118">某些連結 Q# 庫可能適用于與您的程式一起運作 Q# ，或與您的主機應用程式整合的其他工具。</span><span class="sxs-lookup"><span data-stu-id="bd077-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="bd077-119">例如，化學連結[庫安裝指示](xref:microsoft.quantum.chemistry.concepts.installation)說明如何搭配 NWChem 計算化學平臺使用[ **Microsoft 量子**套件](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)，以及如何安裝 `qdk-chem` 命令列工具來處理量子化學資料。</span><span class="sxs-lookup"><span data-stu-id="bd077-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="bd077-120">Q#命令列應用程式或 .NET interopability</span><span class="sxs-lookup"><span data-stu-id="bd077-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="bd077-121">**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 中，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案。</span><span class="sxs-lookup"><span data-stu-id="bd077-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="bd077-122">例如，若要新增[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)封裝，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bd077-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="bd077-123">**Visual Studio：** 如果您使用 Visual Studio 2019 或更新版本，您可以 Q# 使用 NuGet 套件管理員新增其他套件。</span><span class="sxs-lookup"><span data-stu-id="bd077-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="bd077-124">若要載入封裝：</span><span class="sxs-lookup"><span data-stu-id="bd077-124">To load a package:</span></span> 
1. <span data-ttu-id="bd077-125">在 Visual Studio 中開啟專案時，從 [**專案**] 功能表選取 [**管理 NuGet 套件 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="bd077-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="bd077-126">按一下 **[流覽]**，選取 [**包含發行**前版本]，並搜尋封裝名稱 "Microsoft. 量子. 數值"。</span><span class="sxs-lookup"><span data-stu-id="bd077-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="bd077-127">這會列出可供下載的套件。</span><span class="sxs-lookup"><span data-stu-id="bd077-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="bd077-128">將滑鼠游標暫留在 [**數值**] 上，然後按一下版本號碼右邊的向下箭號，即可安裝數值套件。</span><span class="sxs-lookup"><span data-stu-id="bd077-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="bd077-129">如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="bd077-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="bd077-130">或者，您可以使用套件管理員主控台，透過命令列介面將數值程式庫新增至您的專案。</span><span class="sxs-lookup"><span data-stu-id="bd077-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![從命令列使用套件管理員主控台](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="bd077-132">從 [套件管理員主控台] 執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bd077-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="bd077-133">如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="bd077-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="bd077-134">我的 Q# 筆記本</span><span class="sxs-lookup"><span data-stu-id="bd077-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="bd077-135">您可以 Q# 使用[ `%package` 魔術命令](xref:microsoft.quantum.iqsharp.magic-ref.package)，讓其他套件可在我的筆記本中使用。</span><span class="sxs-lookup"><span data-stu-id="bd077-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="bd077-136">例如，若要新增用於我筆記本的[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)封裝 Q# ，請在筆記本資料格中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bd077-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="bd077-137">在此命令之後，筆記本中的任何資料格都可以使用此套件。</span><span class="sxs-lookup"><span data-stu-id="bd077-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="bd077-138">若要從 Q# 目前工作區中的程式碼提供封裝，請在新增封裝之後重載工作區：</span><span class="sxs-lookup"><span data-stu-id="bd077-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="bd077-139">Python 互通性</span><span class="sxs-lookup"><span data-stu-id="bd077-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="bd077-140">您可以使用方法，讓其他套件可在 Python 主機程式中使用 [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) 。</span><span class="sxs-lookup"><span data-stu-id="bd077-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="bd077-141">例如，若要新增要在我的筆記本中使用的 [[**量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)] 套件 Q# ，請執行下列 Python 程式碼：</span><span class="sxs-lookup"><span data-stu-id="bd077-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="bd077-142">在此命令之後，會將封裝提供給使用編譯的任何程式 Q# 代碼 `qsharp.compile` 。</span><span class="sxs-lookup"><span data-stu-id="bd077-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="bd077-143">若要從 Q# 目前工作區中的程式碼提供封裝，請在新增封裝之後重載工作區：</span><span class="sxs-lookup"><span data-stu-id="bd077-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
