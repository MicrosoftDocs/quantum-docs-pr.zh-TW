---
title: Q# 程式設計語言和 QDK 是什麼？
description: 了解 Microsoft Quantum 開發套件、Q# 程式設計語言，以及要如何建立量子程式。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
ms.openlocfilehash: 55ac946aa935d3748b36ac99096a89d0db686835
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433022"
---
# <a name="what-are-the-q-programming-language-and-qdk"></a><span data-ttu-id="0c268-103">Q# 程式設計語言和 QDK 是什麼？</span><span class="sxs-lookup"><span data-stu-id="0c268-103">What are the Q# programming language and QDK?</span></span>

<span data-ttu-id="0c268-104">Q# 是 Microsoft 的開放原始碼程式設計語言，可用來開發和執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="0c268-104">Q# is Microsoft’s open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="0c268-105">其屬於 Quantum 開發套件 (QDK) 的一部分，內含 [Q# 程式庫](xref:microsoft.quantum.libraries)、[量子模擬器](xref:microsoft.quantum.machines)、[適用於其他程式設計環境的擴充功能](xref:microsoft.quantum.install)和 [API 文件](xref:microsoft.quantum.standardlibsintro)。</span><span class="sxs-lookup"><span data-stu-id="0c268-105">It’s part of the Quantum Development Kit (QDK), which includes [Q# libraries](xref:microsoft.quantum.libraries), [quantum simulators](xref:microsoft.quantum.machines), [extensions for other programming environments](xref:microsoft.quantum.install), and [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span> <span data-ttu-id="0c268-106">除了標準的 Q# 程式庫之外，QDK 還包含化學、機器學習與數值程式庫。</span><span class="sxs-lookup"><span data-stu-id="0c268-106">In addition to the Standard Q# library, the QDK includes Chemistry, Machine Learning, and Numeric libraries.</span></span>

<span data-ttu-id="0c268-107">作為程式設計語言，Q# 擷取了 Python、C# 和 F# 中的熟悉元素，並可支援使用迴圈、if/then 陳述式和常見資料類型來撰寫程式的基本程序模型。</span><span class="sxs-lookup"><span data-stu-id="0c268-107">As a programming language, Q# draws familiar elements from Python, C#, and F# and supports a basic procedural model for writing programs with loops, if/then statements, and common data types.</span></span> <span data-ttu-id="0c268-108">其也引進了新的量子特有資料結構和運算。</span><span class="sxs-lookup"><span data-stu-id="0c268-108">It also introduces new quantum-specific data structures and operations.</span></span>

## <a name="what-can-i-do-with-the-qdk"></a><span data-ttu-id="0c268-109">QDK 有何用途？</span><span class="sxs-lookup"><span data-stu-id="0c268-109">What can I do with the QDK?</span></span>

<span data-ttu-id="0c268-110">QDK 是適用於 Q# 的完整功能開發套件，您可與常用的工具和語言搭配使用以便開發可在各種環境中執行的量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="0c268-110">The QDK is a full-featured development kit for Q# that you can use with common tools and languages to develop quantum applications that you can run in various environments.</span></span> <span data-ttu-id="0c268-111">Q# 程式可作為命令列應用程式來執行、透過 Jupyter Notebook 來執行，也可以使用 Python 或 .NET 主機程式來執行。</span><span class="sxs-lookup"><span data-stu-id="0c268-111">Q# programs can run as a command-line app, through Jupyter Notebooks, or use a Python or .NET host program.</span></span>

### <a name="develop-in-common-tools-and-environments"></a><span data-ttu-id="0c268-112">在常見的工具和環境中進行開發</span><span class="sxs-lookup"><span data-stu-id="0c268-112">Develop in common tools and environments</span></span>

<span data-ttu-id="0c268-113">請將量子開發與 [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone) 和 [Jupyter Notebook](xref:microsoft.quantum.install.jupyter) 進行整合。</span><span class="sxs-lookup"><span data-stu-id="0c268-113">Integrate your quantum development with [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone), and [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span></span> <span data-ttu-id="0c268-114">使用內建的 API 來將您的程式與 [Python](xref:microsoft.quantum.install.python) 和 [.NET](xref:microsoft.quantum.install.cs) 主機語言配對。</span><span class="sxs-lookup"><span data-stu-id="0c268-114">Use the built-in APIs for pairing your programs with [Python](xref:microsoft.quantum.install.python) and [.NET](xref:microsoft.quantum.install.cs) host languages.</span></span>

### <a name="try-quantum-operations-and-domain-specific-libraries"></a><span data-ttu-id="0c268-115">嘗試量子運算和領域特有程式庫</span><span class="sxs-lookup"><span data-stu-id="0c268-115">Try quantum operations and domain-specific libraries</span></span>

<span data-ttu-id="0c268-116">撰寫並測試量子演算法，以探索疊加、糾纏和其他量子運算。</span><span class="sxs-lookup"><span data-stu-id="0c268-116">Write and test quantum algorithms to explore superposition, entanglement, and other quantum operations.</span></span> <span data-ttu-id="0c268-117">Q# 程式庫可讓您執行複雜的量子運算，而不必設計低層級的運算序列。</span><span class="sxs-lookup"><span data-stu-id="0c268-117">The Q# libraries enable you to run complex quantum operations without having to design low-level operation sequences.</span></span>

### <a name="run-programs-in-simulators"></a><span data-ttu-id="0c268-118">在模擬器中執行程式</span><span class="sxs-lookup"><span data-stu-id="0c268-118">Run programs in simulators</span></span>

<span data-ttu-id="0c268-119">請在全狀態的量子模擬器 (範圍受限的 Toffoli 模擬器) 上執行您的量子程式，或在不同的資源估算器中測試您的 Q# 程式碼。</span><span class="sxs-lookup"><span data-stu-id="0c268-119">Run your quantum programs on a full-state quantum simulator, a limited-scope Toffoli simulator, or test your Q# code in different resource estimators.</span></span> 

## <a name="where-can-i-learn-more"></a><span data-ttu-id="0c268-120">哪裡可以深入了解？</span><span class="sxs-lookup"><span data-stu-id="0c268-120">Where can I learn more?</span></span>

|||
| ---- | ---- |
| <span data-ttu-id="0c268-121">**我是量子運算的新手**</span><span class="sxs-lookup"><span data-stu-id="0c268-121">**I'm new to quantum computing**</span></span> | <span data-ttu-id="0c268-122">檢閱[重要概念](xref:microsoft.quantum.overview.understanding)中的一些量子物理和量子運算基本知識。</span><span class="sxs-lookup"><span data-stu-id="0c268-122">Review some basics of quantum physics and quantum computing in [Key Concepts](xref:microsoft.quantum.overview.understanding).</span></span>|
| <span data-ttu-id="0c268-123">**我想要深入了解 Q# 語言**</span><span class="sxs-lookup"><span data-stu-id="0c268-123">**I want to dive deeper into the Q# language**</span></span> | <span data-ttu-id="0c268-124">在 [Q# 使用者指南](xref:microsoft.quantum.guide)中探索類型、運算式、變數和量子程式結構。</span><span class="sxs-lookup"><span data-stu-id="0c268-124">Explore types, expressions, variables, and quantum program structure in the [Q# User Guide](xref:microsoft.quantum.guide).</span></span>|
| <span data-ttu-id="0c268-125">**我想要直接開始撰寫量子程式**</span><span class="sxs-lookup"><span data-stu-id="0c268-125">**I just want to start writing quantum programs**</span></span> | <span data-ttu-id="0c268-126">在[快速入門](xref:microsoft.quantum.install)中設定您的 Q# 環境並開始撰寫量子程式。</span><span class="sxs-lookup"><span data-stu-id="0c268-126">Set up your Q# environment and start writing quantum programs in [QuickStarts](xref:microsoft.quantum.install).</span></span>|

## <a name="how-does-q-work"></a><span data-ttu-id="0c268-127">Q# 的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="0c268-127">How does Q# work?</span></span>

<span data-ttu-id="0c268-128">Q# 程式可以編譯成獨立的命令列應用程式，或由以 Python 或 .NET 語言撰寫的主機程式加以呼叫。</span><span class="sxs-lookup"><span data-stu-id="0c268-128">A Q# program can compile into a standalone command line application or be called by a host program that is written either in Python or a .NET language.</span></span>

<span data-ttu-id="0c268-129">當您編譯和執行程式時，程式會建立量子模擬器的執行個體，並於其中傳入 Q# 程式碼。</span><span class="sxs-lookup"><span data-stu-id="0c268-129">When you compile and run the program, it creates an instance of the quantum simulator and passes the Q# code to it.</span></span> <span data-ttu-id="0c268-130">模擬器會使用 Q# 程式碼來建立量子位元(模擬量子粒子)，並套用轉換來修改其狀態。</span><span class="sxs-lookup"><span data-stu-id="0c268-130">The simulator uses the Q# code to create qubits (simulations of quantum particles) and apply transformations to modify their state.</span></span> <span data-ttu-id="0c268-131">然後，模擬器中的量子運算結果會傳回給程式。</span><span class="sxs-lookup"><span data-stu-id="0c268-131">The results of the quantum operations in the simulator are then returned to the program.</span></span>  

<span data-ttu-id="0c268-132">在模擬器中隔離 Q# 程式碼可確保演算法會遵循量子物理定律，並可在量子電腦上正確執行。</span><span class="sxs-lookup"><span data-stu-id="0c268-132">Isolating the Q# code in the simulator ensures that the algorithms follow the laws of quantum physics and can run correctly on quantum computers.</span></span>

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a><span data-ttu-id="0c268-134">要如何使用 QDK？</span><span class="sxs-lookup"><span data-stu-id="0c268-134">How do I use the QDK?</span></span>

<span data-ttu-id="0c268-135">為了撰寫和執行 Q# 程式所需的一切資源 (包括 Q# 編譯器、Q# 程式庫和量子模擬器) 都可以從本機電腦安裝及執行。</span><span class="sxs-lookup"><span data-stu-id="0c268-135">Everything you need to write and run Q# programs, including the Q# compiler, the Q# libraries, and the quantum simulators, can be installed and run from your local computer.</span></span> <span data-ttu-id="0c268-136">最終，您將能夠在實際的量子電腦上遠端執行 Q# 程式，但在這之前，QDK 所提供的量子模擬器會提供正確且可靠的結果。</span><span class="sxs-lookup"><span data-stu-id="0c268-136">Eventually you will be able to run your Q# programs remotely on an actual quantum computer, but until then the quantum simulators provided with the QDK provide accurate and reliable results.</span></span>

- <span data-ttu-id="0c268-137">[從命令列執行 Q#](xref:microsoft.quantum.install.standalone) 是能夠最快開始使用的方式。</span><span class="sxs-lookup"><span data-stu-id="0c268-137">Running [Q# from the command line](xref:microsoft.quantum.install.standalone) is the quickest way to get started.</span></span>

- <span data-ttu-id="0c268-138">[使用 IQ# 執行獨立的 Jupyter Notebook](xref:microsoft.quantum.install.jupyter)，IQ# 是用來編譯和模擬 Q# 程式並將其視覺化的 Jupyter 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="0c268-138">Run standalone [Jupyter Notebooks with IQ#](xref:microsoft.quantum.install.jupyter), a Jupyter extension for compiling, simulating, and visualizing Q# programs.</span></span>

- <span data-ttu-id="0c268-139">如果您熟悉 [Python](xref:microsoft.quantum.install.python)，就可以用 Python 作為要開始使用的主機程式設計平台。</span><span class="sxs-lookup"><span data-stu-id="0c268-139">If you are familiar with [Python](xref:microsoft.quantum.install.python), you can use it as a host programming platform to get started.</span></span> <span data-ttu-id="0c268-140">Python 不僅廣為開發人員使用，連科學家、研究人員和老師也都在使用。</span><span class="sxs-lookup"><span data-stu-id="0c268-140">Python enjoys widespread use not only among developers, but also scientists, researchers and teachers.</span></span>

- <span data-ttu-id="0c268-141">如果您已有 [C#、F# 或 VB.NET](xref:microsoft.quantum.install.cs) 的經驗，而且熟悉 Visual Studio 開發環境，則您需要將幾個擴充功能新增至 Visual Studio 以使其做好準備而能用於 Q#。</span><span class="sxs-lookup"><span data-stu-id="0c268-141">If you already have experience with [C#, F#, or VB.NET](xref:microsoft.quantum.install.cs) and are familiar with the Visual Studio development environment, there are just a few extensions you need to add to Visual Studio to prepare it for Q#.</span></span>  

## <a name="summary"></a><span data-ttu-id="0c268-142">摘要</span><span class="sxs-lookup"><span data-stu-id="0c268-142">Summary</span></span>

<span data-ttu-id="0c268-143">Q# 是一種可用來開發量子程式的開放原始碼程式設計語言。</span><span class="sxs-lookup"><span data-stu-id="0c268-143">Q# is an open-source programming language for developing quantum programs.</span></span> <span data-ttu-id="0c268-144">其具有可讓您建立複雜量子運算的程式庫，並有量子模擬器可供正確地執行和測試您的程式。</span><span class="sxs-lookup"><span data-stu-id="0c268-144">It has libraries that let you create complex quantum operations, and quantum simulators to accurately run and test your programs.</span></span> <span data-ttu-id="0c268-145">Q# 程式可作為獨立應用程式來執行，也可以從 Python 或 .NET 主機程式中加以呼叫，並可從您的本機電腦來撰寫、執行和測試。</span><span class="sxs-lookup"><span data-stu-id="0c268-145">Q# programs can run as standalone apps or be called from a Python or .NET host program, and can be written, run, and tested from your local computer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c268-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0c268-146">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0c268-147">量子運算的線性代數</span><span class="sxs-lookup"><span data-stu-id="0c268-147">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)
