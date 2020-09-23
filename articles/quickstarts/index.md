---
title: 設定 Microsoft Quantum 開發套件 (QDK)
description: 了解如何為不同環境設定 Microsoft Quantum 開發套件。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834477"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="426ef-103">設定 Microsoft Quantum 開發套件 (QDK)</span><span class="sxs-lookup"><span data-stu-id="426ef-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="426ef-104">了解如何設定您環境的 Microsoft Quantum 開發套件 (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="426ef-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="426ef-105">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="426ef-105">The QDK consists of:</span></span>

- <span data-ttu-id="426ef-106">Q#程式設計語言</span><span class="sxs-lookup"><span data-stu-id="426ef-106">The Q# programming language</span></span>
- <span data-ttu-id="426ef-107">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="426ef-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="426ef-108">適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式</span><span class="sxs-lookup"><span data-stu-id="426ef-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="426ef-109">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="426ef-109">Tools to facilitate your development</span></span>

<span data-ttu-id="426ef-110">Q# 程式可以使用 Visual Studio Code、Visual Studio，透過具有 IQ# Jupyter 核心的 Jupyter Notebook，或以 Python 或.NET language (C#, F#).撰寫的主機程式配對，並以獨立應用程式的形式執行。</span><span class="sxs-lookup"><span data-stu-id="426ef-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="426ef-111">您也可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker)，在線上執行 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="426ef-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="426ef-112">設定 QDK 的選項</span><span class="sxs-lookup"><span data-stu-id="426ef-112">Options for setting up the QDK</span></span>

<span data-ttu-id="426ef-113">您可以透過三種方式來使用 QDK：</span><span class="sxs-lookup"><span data-stu-id="426ef-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="426ef-114">在本機安裝 QDK</span><span class="sxs-lookup"><span data-stu-id="426ef-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="426ef-115">線上使用 QDK</span><span class="sxs-lookup"><span data-stu-id="426ef-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="426ef-116">使用 QDK Docker 映像</span><span class="sxs-lookup"><span data-stu-id="426ef-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="426ef-117">在本機安裝 QDK</span><span class="sxs-lookup"><span data-stu-id="426ef-117">Install the QDK locally</span></span>

<span data-ttu-id="426ef-118">您可以在大部分的 [我的最愛] IDE 中開發 Q# 程式碼，以及將 Q# 與其他語言，例如 Python 和 .NET (C#, F#) 進行整合。</span><span class="sxs-lookup"><span data-stu-id="426ef-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="426ef-119">**VS Code<br>(2019 或更新版本)**</span><span class="sxs-lookup"><span data-stu-id="426ef-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="426ef-120">**Visual Studio <br>(2019 或更新版本)**</span><span class="sxs-lookup"><span data-stu-id="426ef-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="426ef-121">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="426ef-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="426ef-122">**命令列**</span><span class="sxs-lookup"><span data-stu-id="426ef-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="426ef-123">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="426ef-123">**OS**</span></span> |<span data-ttu-id="426ef-124">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="426ef-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="426ef-125">僅限 Windows</span><span class="sxs-lookup"><span data-stu-id="426ef-125">Windows only</span></span> |<span data-ttu-id="426ef-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="426ef-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="426ef-127">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="426ef-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="426ef-128">**Q# 獨立**</span><span class="sxs-lookup"><span data-stu-id="426ef-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="426ef-129">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="426ef-130">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="426ef-131">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="426ef-132">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="426ef-133">**Q#  和 Python**</span><span class="sxs-lookup"><span data-stu-id="426ef-133">**Q#  and Python**</span></span> |[<span data-ttu-id="426ef-134">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="426ef-135">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="426ef-136">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="426ef-137">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="426ef-138">**Q# 和 .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="426ef-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="426ef-139">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="426ef-140">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="426ef-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="426ef-141">&#10006;</span></span> |[<span data-ttu-id="426ef-142">安裝</span><span class="sxs-lookup"><span data-stu-id="426ef-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="426ef-143">線上使用 QDK</span><span class="sxs-lookup"><span data-stu-id="426ef-143">Use the QDK Online</span></span>

<span data-ttu-id="426ef-144">您也可以使用下列選項來開發 Q# 程式碼，而不需要在本機上安裝任何東西：</span><span class="sxs-lookup"><span data-stu-id="426ef-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="426ef-145">資源</span><span class="sxs-lookup"><span data-stu-id="426ef-145">Resource</span></span>|<span data-ttu-id="426ef-146">優點</span><span class="sxs-lookup"><span data-stu-id="426ef-146">Advantages</span></span>|<span data-ttu-id="426ef-147">限制</span><span class="sxs-lookup"><span data-stu-id="426ef-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="426ef-148">**Visual Studio 程式碼空間**</span><span class="sxs-lookup"><span data-stu-id="426ef-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="426ef-149">豐富的線上開發環境</span><span class="sxs-lookup"><span data-stu-id="426ef-149">A rich online development environment</span></span>  |<span data-ttu-id="426ef-150">需要 Azure 訂用帳戶和方案</span><span class="sxs-lookup"><span data-stu-id="426ef-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="426ef-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="426ef-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="426ef-152">免費的線上筆記本體驗</span><span class="sxs-lookup"><span data-stu-id="426ef-152">Free online notebook experience</span></span> |<span data-ttu-id="426ef-153">無持續性</span><span class="sxs-lookup"><span data-stu-id="426ef-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="426ef-154">使用 QDK 搭配 Docker</span><span class="sxs-lookup"><span data-stu-id="426ef-154">Use the QDK with Docker</span></span>

<span data-ttu-id="426ef-155">您可以透過任何支援 Docker 映像的服務 (例如 ACI)，在本機 Docker 安裝或雲端中使用我們的 QDK Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="426ef-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="426ef-156">您可以從 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下載 IQ# Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="426ef-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="426ef-157">您也可以使用 Docker 搭配 Visual Studio Code 遠端開發容器，以快速定義開發環境。</span><span class="sxs-lookup"><span data-stu-id="426ef-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="426ef-158">如需 VS Code 開發容器的詳細資訊，請參閱 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。</span><span class="sxs-lookup"><span data-stu-id="426ef-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="426ef-159">後續步驟</span><span class="sxs-lookup"><span data-stu-id="426ef-159">Next steps</span></span>

<span data-ttu-id="426ef-160">在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中有這些設定的工作流程描述和比較。</span><span class="sxs-lookup"><span data-stu-id="426ef-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
