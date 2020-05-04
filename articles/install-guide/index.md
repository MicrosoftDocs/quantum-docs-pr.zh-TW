---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
description: 如何安裝適用於 C#、Python 和 Jupyter Notebook 環境的 Microsoft Quantum Development Kit。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680184"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="6ed51-103">安裝 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="6ed51-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="6ed51-104">了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="6ed51-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="6ed51-105">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="6ed51-105">The QDK consists of:</span></span>

- <span data-ttu-id="6ed51-106">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="6ed51-106">the Q# programming language</span></span>
- <span data-ttu-id="6ed51-107">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="6ed51-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="6ed51-108">適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式</span><span class="sxs-lookup"><span data-stu-id="6ed51-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="6ed51-109">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="6ed51-109">tools to facilitate your development</span></span>

<span data-ttu-id="6ed51-110">Q# 程式通常會搭配以 .NET 語言 (通常是 C#) 或 Python 撰寫的主機程式。</span><span class="sxs-lookup"><span data-stu-id="6ed51-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="6ed51-111">這可讓我們從傳統程式內呼叫量子作業。</span><span class="sxs-lookup"><span data-stu-id="6ed51-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="6ed51-112">除此之外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。</span><span class="sxs-lookup"><span data-stu-id="6ed51-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="6ed51-113">QDK 適用於多個開發環境。</span><span class="sxs-lookup"><span data-stu-id="6ed51-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="6ed51-114">從下列各節中選取您偏好的設定：</span><span class="sxs-lookup"><span data-stu-id="6ed51-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="6ed51-115">[Q# 命令列應用程式：](xref:microsoft.quantum.install.standalone)如果您想要從命令列使用 Q #，請選擇此方法。</span><span class="sxs-lookup"><span data-stu-id="6ed51-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="6ed51-116">這不需要像下列選項的驅動程式或主機程式。</span><span class="sxs-lookup"><span data-stu-id="6ed51-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="6ed51-117">[安裝 Q# for Jupyter Notebook：](xref:microsoft.quantum.install.jupyter)選擇此環境，以內嵌文字的儲存格執行 Q# 程式碼，或建立量子計算互動式教學課程。</span><span class="sxs-lookup"><span data-stu-id="6ed51-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="6ed51-118">[使用 Q# 和 Python 開發：](xref:microsoft.quantum.install.python)如果您想要結合 Python 和 Q# 來建立可呼叫 Q# 作業的 Python 主機程式。</span><span class="sxs-lookup"><span data-stu-id="6ed51-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="6ed51-119">[使用 Q # 和 C# 或 F# 開發：](xref:microsoft.quantum.install.cs)如果您想要結合 C# 或 F# 和 Q # 以建立呼叫 Q # 作業的 .NET 主機程式。</span><span class="sxs-lookup"><span data-stu-id="6ed51-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
