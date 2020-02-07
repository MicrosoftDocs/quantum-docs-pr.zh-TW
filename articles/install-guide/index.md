---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036503"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="896e8-102">安裝 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="896e8-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="896e8-103">了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="896e8-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="896e8-104">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="896e8-104">The QDK consists of:</span></span>

- <span data-ttu-id="896e8-105">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="896e8-105">the Q# programming language</span></span>
- <span data-ttu-id="896e8-106">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="896e8-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="896e8-107">適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式</span><span class="sxs-lookup"><span data-stu-id="896e8-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="896e8-108">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="896e8-108">tools to facilitate your development</span></span>

<span data-ttu-id="896e8-109">Q# 程式通常會搭配以 .NET 語言 (通常是 C#) 或 Python 撰寫的主機程式。</span><span class="sxs-lookup"><span data-stu-id="896e8-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="896e8-110">這可讓我們從傳統程式內呼叫量子作業。</span><span class="sxs-lookup"><span data-stu-id="896e8-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="896e8-111">除此之外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。</span><span class="sxs-lookup"><span data-stu-id="896e8-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="896e8-112">QDK 適用於多個開發環境。</span><span class="sxs-lookup"><span data-stu-id="896e8-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="896e8-113">從下列各節中選取您偏好的設定：</span><span class="sxs-lookup"><span data-stu-id="896e8-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="896e8-114">[安裝 Q# for C#：](xref:microsoft.quantum.install.cs)如果您想要結合 C# 和 Q# 來建立可呼叫 Q# 作業的 C# 主機程式，請選擇此環境。</span><span class="sxs-lookup"><span data-stu-id="896e8-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="896e8-115">[安裝 Q# for Python：](xref:microsoft.quantum.install.python)如果您想要結合 Python 和 Q# 來建立可呼叫 Q# 作業的 Python 主機程式，請選擇此環境。</span><span class="sxs-lookup"><span data-stu-id="896e8-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="896e8-116">[安裝 Q# for Jupyter Notebook：](xref:microsoft.quantum.install.jupyter)選擇此環境，以內嵌文字的儲存格執行 Q# 程式碼，或建立量子計算互動式教學課程。</span><span class="sxs-lookup"><span data-stu-id="896e8-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="896e8-117">如果您想要結合 Q # 與外部傳統主機程式，請勿選擇此環境。</span><span class="sxs-lookup"><span data-stu-id="896e8-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
