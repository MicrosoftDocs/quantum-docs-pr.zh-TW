---
title: 設定 Microsoft Quantum 開發套件 (QDK)
description: 了解如何為不同環境設定 Microsoft Quantum 開發套件。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859034"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="13e33-103">設定 Microsoft Quantum 開發套件 (QDK)</span><span class="sxs-lookup"><span data-stu-id="13e33-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="13e33-104">了解如何設定您環境的 Microsoft Quantum 開發套件 (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="13e33-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="13e33-105">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="13e33-105">The QDK consists of:</span></span>

- <span data-ttu-id="13e33-106">Q#程式設計語言</span><span class="sxs-lookup"><span data-stu-id="13e33-106">The Q# programming language</span></span>
- <span data-ttu-id="13e33-107">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="13e33-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="13e33-108">適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式</span><span class="sxs-lookup"><span data-stu-id="13e33-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="13e33-109">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="13e33-109">Tools to facilitate your development</span></span>

<span data-ttu-id="13e33-110">Q# 程式可以使用 Visual Studio Code、Visual Studio，透過具有 IQ# Jupyter 核心的 Jupyter Notebook，或以 Python 或.NET language (C#, F#).撰寫的主機程式配對，並以獨立應用程式的形式執行。</span><span class="sxs-lookup"><span data-stu-id="13e33-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="13e33-111">您也可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker)，在線上執行 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="13e33-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="13e33-112">設定 QDK 的選項</span><span class="sxs-lookup"><span data-stu-id="13e33-112">Options for setting up the QDK</span></span>

<span data-ttu-id="13e33-113">您可以透過三種方式來使用 QDK：</span><span class="sxs-lookup"><span data-stu-id="13e33-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="13e33-114">在本機安裝 QDK</span><span class="sxs-lookup"><span data-stu-id="13e33-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="13e33-115">線上使用 QDK</span><span class="sxs-lookup"><span data-stu-id="13e33-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="13e33-116">使用 QDK Docker 映像</span><span class="sxs-lookup"><span data-stu-id="13e33-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="13e33-117">在本機安裝 QDK</span><span class="sxs-lookup"><span data-stu-id="13e33-117">Install the QDK locally</span></span>

<span data-ttu-id="13e33-118">您可以在大部分的 [我的最愛] IDE 中開發 Q# 程式碼，以及將 Q# 與其他語言，例如 Python 和 .NET (C#, F#) 進行整合。</span><span class="sxs-lookup"><span data-stu-id="13e33-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="13e33-119"><b>VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="13e33-119"><b>VS Code</span></span><br><span data-ttu-id="13e33-120">(2019 或更新版本)</b></span><span class="sxs-lookup"><span data-stu-id="13e33-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="13e33-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13e33-121"><b>Visual Studio</span></span><br><span data-ttu-id="13e33-122">(2019 或更新版本)</b></span><span class="sxs-lookup"><span data-stu-id="13e33-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="13e33-123"><b>Jupyter Notebook</b></span><span class="sxs-lookup"><span data-stu-id="13e33-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="13e33-124"><b>命令列</b></span><span class="sxs-lookup"><span data-stu-id="13e33-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="13e33-125"><b>OS 支援：</b></span><span class="sxs-lookup"><span data-stu-id="13e33-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="13e33-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="13e33-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="13e33-127">僅限 Windows</span><span class="sxs-lookup"><span data-stu-id="13e33-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="13e33-128">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="13e33-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="13e33-129">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="13e33-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="13e33-130"><b>Q# 獨立</b></span><span class="sxs-lookup"><span data-stu-id="13e33-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="13e33-131"><a href="xref:microsoft.quantum.install.standalone">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-132"><a href="xref:microsoft.quantum.install.standalone">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-133"><a href="xref:microsoft.quantum.install.jupyter">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-134"><a href="xref:microsoft.quantum.install.standalone">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="13e33-135"><b>Q# 和 Python</b></span><span class="sxs-lookup"><span data-stu-id="13e33-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="13e33-136"><a href="xref:microsoft.quantum.install.python">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-137"><a href="xref:microsoft.quantum.install.python">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-138"><a href="xref:microsoft.quantum.install.python">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-139"><a href="xref:microsoft.quantum.install.python">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="13e33-140"><b>Q# 和 .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="13e33-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="13e33-141"><a href="xref:microsoft.quantum.install.cs">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-142"><a href="xref:microsoft.quantum.install.cs">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13e33-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="13e33-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="13e33-144"><a href="xref:microsoft.quantum.install.cs">安裝</a></span><span class="sxs-lookup"><span data-stu-id="13e33-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="13e33-145">線上使用 QDK</span><span class="sxs-lookup"><span data-stu-id="13e33-145">Use the QDK Online</span></span>

<span data-ttu-id="13e33-146">您也可以使用下列選項來開發 Q# 程式碼，而不需要在本機上安裝任何東西：</span><span class="sxs-lookup"><span data-stu-id="13e33-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="13e33-147">資源</span><span class="sxs-lookup"><span data-stu-id="13e33-147">Resource</span></span>|<span data-ttu-id="13e33-148">優點</span><span class="sxs-lookup"><span data-stu-id="13e33-148">Advantages</span></span>|<span data-ttu-id="13e33-149">限制</span><span class="sxs-lookup"><span data-stu-id="13e33-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="13e33-150">**Visual Studio 程式碼空間**</span><span class="sxs-lookup"><span data-stu-id="13e33-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="13e33-151">豐富的線上開發環境</span><span class="sxs-lookup"><span data-stu-id="13e33-151">A rich online development environment</span></span>  |<span data-ttu-id="13e33-152">需要 Azure 訂用帳戶和方案</span><span class="sxs-lookup"><span data-stu-id="13e33-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="13e33-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="13e33-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="13e33-154">免費的線上筆記本體驗</span><span class="sxs-lookup"><span data-stu-id="13e33-154">Free online notebook experience</span></span> |<span data-ttu-id="13e33-155">無持續性</span><span class="sxs-lookup"><span data-stu-id="13e33-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="13e33-156">使用 QDK 搭配 Docker</span><span class="sxs-lookup"><span data-stu-id="13e33-156">Use the QDK with Docker</span></span>

<span data-ttu-id="13e33-157">您可以透過任何支援 Docker 映像的服務 (例如 ACI)，在本機 Docker 安裝或雲端中使用我們的 QDK Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="13e33-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="13e33-158">您可以從 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下載 IQ# Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="13e33-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="13e33-159">您也可以使用 Docker 搭配 Visual Studio Code 遠端開發容器，以快速定義開發環境。</span><span class="sxs-lookup"><span data-stu-id="13e33-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="13e33-160">如需 VS Code 開發容器的詳細資訊，請參閱 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。</span><span class="sxs-lookup"><span data-stu-id="13e33-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13e33-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="13e33-161">Next steps</span></span>

<span data-ttu-id="13e33-162">在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中有這些設定的工作流程描述和比較。</span><span class="sxs-lookup"><span data-stu-id="13e33-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
