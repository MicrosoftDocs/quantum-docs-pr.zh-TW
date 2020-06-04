---
title: 安裝 Microsoft Quantum Development Kit (QDK)
description: 如何為不同環境安裝 Microsoft Quantum Development Kit。
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327557"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c9df7-103">安裝 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c9df7-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c9df7-104">了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="c9df7-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="c9df7-105">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="c9df7-105">The QDK consists of:</span></span>

- <span data-ttu-id="c9df7-106">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="c9df7-106">The Q# programming language</span></span>
- <span data-ttu-id="c9df7-107">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="c9df7-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="c9df7-108">適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式</span><span class="sxs-lookup"><span data-stu-id="c9df7-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="c9df7-109">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="c9df7-109">Tools to facilitate your development</span></span>

<span data-ttu-id="c9df7-110">Q# 程式可以使用 Visual Studio Code、Visual Studio 或透過具有 IQ # Jupyter 核心的 Jupyter Notebook，以獨立應用程式的形式執行。</span><span class="sxs-lookup"><span data-stu-id="c9df7-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="c9df7-111">也可以與以 .NET 語言 (通常是 C#) 或 Python 撰寫的主機程式配對，讓您可以從傳統程式內部呼叫量子作業。</span><span class="sxs-lookup"><span data-stu-id="c9df7-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="c9df7-112">QDK 適用於多個開發環境。</span><span class="sxs-lookup"><span data-stu-id="c9df7-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="c9df7-113">從下方選取您慣用的設定：</span><span class="sxs-lookup"><span data-stu-id="c9df7-113">Select your preferred setup from:</span></span>

<span data-ttu-id="c9df7-114">[使用 Q# 命令列應用程式開發](xref:microsoft.quantum.install.standalone) - 選擇此方法以從命令列使用 Q #。</span><span class="sxs-lookup"><span data-stu-id="c9df7-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="c9df7-115">這不需要像下列選項的驅動程式或主機程式。</span><span class="sxs-lookup"><span data-stu-id="c9df7-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="c9df7-116">[使用 Jupyter Notebook 開發](xref:microsoft.quantum.install.jupyter) - 選取此環境，以內嵌文字的儲存格執行 Q# 程式碼，或建立量子計算互動式教學課程。</span><span class="sxs-lookup"><span data-stu-id="c9df7-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="c9df7-117">[使用 Q# 和 Python 開發](xref:microsoft.quantum.install.python) - 讓您結合 Python 和 Q# 來建立可呼叫 Q# 作業的 Python 主機程式。</span><span class="sxs-lookup"><span data-stu-id="c9df7-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="c9df7-118">[使用 Q # 和 .NET 開發](xref:microsoft.quantum.install.cs) - 將 C#、F# 或 VB.NET 與 Q# 結合，以建立呼叫 Q# 作業的 .NET 主機程式。</span><span class="sxs-lookup"><span data-stu-id="c9df7-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
