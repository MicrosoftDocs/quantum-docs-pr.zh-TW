---
title: Q# 使用者指南
description: 使用者指南的用途和內容概觀
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231752"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="d5864-103">Q# 使用者指南</span><span class="sxs-lookup"><span data-stu-id="d5864-103">The Q# User Guide</span></span>

<span data-ttu-id="d5864-104">歡迎使用 Q# 使用者指南！</span><span class="sxs-lookup"><span data-stu-id="d5864-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="d5864-105">在本指南的不同主題中，我們將介紹使用 Q# 開發量子程式的一些基本概念。</span><span class="sxs-lookup"><span data-stu-id="d5864-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="d5864-106">如需 Q# 量子程式設計語言的完整規格和檔，請參閱 [Q# 語言指南](xref:microsoft.quantum.qsharp.index)。</span><span class="sxs-lookup"><span data-stu-id="d5864-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="d5864-107">使用者指南內容</span><span class="sxs-lookup"><span data-stu-id="d5864-107">User Guide Contents</span></span>

- <span data-ttu-id="d5864-108">[Q#程式](xref:microsoft.quantum.guide.programs)：Q# 中的量子程式快速簡介。</span><span class="sxs-lookup"><span data-stu-id="d5864-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="d5864-109">[執行 Q# 程式](xref:microsoft.quantum.guide.host-programs)的方式：說明如何執行 Q# 程式，並概述您可以呼叫程式的各種方法：從命令列、從 Q# Jupyter Notebook、或從以 Python 或 .NET 語言撰寫的傳統主機程式。</span><span class="sxs-lookup"><span data-stu-id="d5864-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="d5864-110">[測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)：詳細說明一些技術，用來確保您的程式碼會執行其作業。</span><span class="sxs-lookup"><span data-stu-id="d5864-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="d5864-111">由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。</span><span class="sxs-lookup"><span data-stu-id="d5864-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="d5864-112">幸運的是，Q# 支援許多設計人員熟悉的傳統偵錯技術，以及屬於量子特有的偵錯技術。</span><span class="sxs-lookup"><span data-stu-id="d5864-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="d5864-113">其中包括在 Q# 中建立和執行單元測試、在程式碼中的值和機率內嵌 *判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。</span><span class="sxs-lookup"><span data-stu-id="d5864-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="d5864-114">後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，[不複製定理](xref:microsoft.quantum.concepts.pauli))，以偵測計算的特定部分。</span><span class="sxs-lookup"><span data-stu-id="d5864-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="d5864-115">量子模擬器和資源估算器</span><span class="sxs-lookup"><span data-stu-id="d5864-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="d5864-116">[量子模擬器和主應用程式](xref:microsoft.quantum.machines)：概述可用的各種模擬器，以及主程式與目標機器如何共同運作，以執行 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="d5864-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="d5864-117">[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)：模擬完整量子狀態的目標機器。</span><span class="sxs-lookup"><span data-stu-id="d5864-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="d5864-118">適用於完整執行或偵錯規模較小的程式 (少於數十個量子位元)</span><span class="sxs-lookup"><span data-stu-id="d5864-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="d5864-119">[資源估算器](xref:microsoft.quantum.machines.resources-estimator)：估算在量子電腦上執行 Q# 作業指定執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="d5864-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="d5864-120">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：執行量子程式，而不實際模擬量子電腦的狀態，因此可以執行使用數千個量子位元的量子程式。</span><span class="sxs-lookup"><span data-stu-id="d5864-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="d5864-121">適用於在量子程式內進行傳統程式碼的偵錯，以及預估所需的資源。</span><span class="sxs-lookup"><span data-stu-id="d5864-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="d5864-122">[Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)：特殊用途的量子模擬器，可對數百萬個量子位元使用，但僅適用於具有一組有限量子作業 (X、CNOT 和多重受控 X) 的程式。</span><span class="sxs-lookup"><span data-stu-id="d5864-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="d5864-123">快速參考指南</span><span class="sxs-lookup"><span data-stu-id="d5864-123">Quick Reference Pages</span></span>

- <span data-ttu-id="d5864-124">[IQ#Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter Notebook 中的 IQ# 魔術命令快速參考頁面。</span><span class="sxs-lookup"><span data-stu-id="d5864-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
