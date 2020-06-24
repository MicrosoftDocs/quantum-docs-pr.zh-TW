---
title: Microsoft 量子數值程式庫-安裝和驗證
description: 瞭解如何將 Microsoft 量子數值程式庫新增至您的 Visual Studio 2019 或更新版本的安裝。
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274703"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="8ccb5-103">數值程式庫安裝和驗證</span><span class="sxs-lookup"><span data-stu-id="8ccb5-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="8ccb5-104">配量開發工具組透過 NuGet 套件提供數值功能的支援 [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) 。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="8ccb5-105">**Visual Studio >= 2019：** 如果您使用 Visual Studio 2019 或更新版本，您可以使用 NuGet 套件管理員新增數值套件。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="8ccb5-106">若要這麼做，請選取 [管理 NuGet 套件 ...]從 Visual Studio 中的 [專案] 功能表項目。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="8ccb5-107">從 [流覽] 索引標籤中，搜尋封裝名稱 "Microsoft. 量子. 數值"</span><span class="sxs-lookup"><span data-stu-id="8ccb5-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="8ccb5-108">請務必勾選「包含發行前版本」</span><span class="sxs-lookup"><span data-stu-id="8ccb5-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="8ccb5-109">這會列出可供下載的套件。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-109">This will list the packages available for download.</span></span>
<span data-ttu-id="8ccb5-110">將滑鼠暫留在 "Microsoft. 量子" 上會向右箭號顯示版本號碼的右方。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="8ccb5-111">按一下箭號以安裝數值套件。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="8ccb5-112">如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="8ccb5-113">或者，您可以使用套件管理員主控台，透過命令列介面將數值程式庫新增至您的專案。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![從命令列使用套件管理員主控台](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="8ccb5-115">從 [套件管理員主控台] 執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8ccb5-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="8ccb5-116">如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="8ccb5-117">**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 中，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案：</span><span class="sxs-lookup"><span data-stu-id="8ccb5-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="8ccb5-118">正在驗證您的安裝</span><span class="sxs-lookup"><span data-stu-id="8ccb5-118">Verifying your installation</span></span>

<span data-ttu-id="8ccb5-119">就像其他的量子開發工具組一樣，數值程式庫隨附的範例可協助您儘快開始使用。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="8ccb5-120">若要使用這些範例來測試您的安裝，請複製[主要的範例存放庫](https://github.com/Microsoft/Quantum)，然後執行其中一個範例。</span><span class="sxs-lookup"><span data-stu-id="8ccb5-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="8ccb5-121">若要執行 [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) 範例：</span><span class="sxs-lookup"><span data-stu-id="8ccb5-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
