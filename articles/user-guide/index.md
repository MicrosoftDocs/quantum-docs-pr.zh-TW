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
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771375"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="6f83e-103">Q# 使用者指南</span><span class="sxs-lookup"><span data-stu-id="6f83e-103">The Q# User Guide</span></span>

<span data-ttu-id="6f83e-104">歡迎使用 Q# 使用者指南！</span><span class="sxs-lookup"><span data-stu-id="6f83e-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="6f83e-105">在本指南提供的不同主題中，會詳細說明 Q# 語言的核心概念，以及撰寫量子程式所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="6f83e-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="6f83e-106">使用者指南內容</span><span class="sxs-lookup"><span data-stu-id="6f83e-106">User Guide Contents</span></span>

- <span data-ttu-id="6f83e-107">[Q# 基本概念](xref:microsoft.quantum.guide.basics)：Q# 程式設計語言的用途和功能概述。</span><span class="sxs-lookup"><span data-stu-id="6f83e-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="6f83e-108">[執行 Q# 程式](xref:microsoft.quantum.guide.host-programs)的方式：說明如何執行 Q# 程式，並概述您可以呼叫程式的各種方法：從命令列、從 Q# Jupyter Notebook、或從以 Python 或 .NET 語言撰寫的傳統主機程式。</span><span class="sxs-lookup"><span data-stu-id="6f83e-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="6f83e-109">Q# 語言</span><span class="sxs-lookup"><span data-stu-id="6f83e-109">Q# Language</span></span>

- <span data-ttu-id="6f83e-110">[Q#](xref:microsoft.quantum.guide.types)中的類型：配置 Q# 類型模型，並描述用於指定和使用類型的語法。</span><span class="sxs-lookup"><span data-stu-id="6f83e-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="6f83e-111">[類型運算式](xref:microsoft.quantum.guide.expressions)：詳細說明如何指定、參考、結合和操作 Q# 中每個類型的值。</span><span class="sxs-lookup"><span data-stu-id="6f83e-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="6f83e-112">使用 Q#</span><span class="sxs-lookup"><span data-stu-id="6f83e-112">Using Q#</span></span>

- <span data-ttu-id="6f83e-113">[Q#檔案結構](xref:microsoft.quantum.guide.filestructure)：描述 `*.qs` Q# 檔案的結構和語法。</span><span class="sxs-lookup"><span data-stu-id="6f83e-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="6f83e-114">[作業和函式](xref:microsoft.quantum.guide.operationsfunctions)：詳細說明 Q# 語言的兩種可呼叫類型：「作業」包含量子位元暫存器上的動作，「函式」則嚴格地處理傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="6f83e-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="6f83e-115">在這裡，您會了解如何定義和呼叫這些類型，包括伴隨 (adjoint) 和受控的量子作業版本。</span><span class="sxs-lookup"><span data-stu-id="6f83e-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="6f83e-116">[變數](xref:microsoft.quantum.guide.variables)：描述 Q# 程式中變數的角色，以及如何有效地運用。</span><span class="sxs-lookup"><span data-stu-id="6f83e-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="6f83e-117">例如，您可以找到繫結範圍的相關資訊，以及不可變和可變變數之間的差異，以及如何指派或重新指派這些變數。</span><span class="sxs-lookup"><span data-stu-id="6f83e-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="6f83e-118">[使用量子位元](xref:microsoft.quantum.guide.qubits)：說明用於處理個別量子和量子系統的 Q# 功能，尤其是對其執行分配、操作和測量的功能。</span><span class="sxs-lookup"><span data-stu-id="6f83e-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="6f83e-119">[控制流程](xref:microsoft.quantum.guide.controlflow)：詳細說明 Q# 中可用的程式設計控制流程模式，其中包括許多標準技術 (例如，條件式流程、for 迴圈、while 迴圈)，以及量子特有的「重複直到成功 (Repeat-Until-Success)」模式。</span><span class="sxs-lookup"><span data-stu-id="6f83e-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional processing, *for* loops, *while* loops) as well as the quantum-specific *Repeat-Until-Success* pattern.</span></span>

- <span data-ttu-id="6f83e-120">[測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)：詳細說明一些技術，用來確保您的程式碼會執行其作業。</span><span class="sxs-lookup"><span data-stu-id="6f83e-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="6f83e-121">由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。</span><span class="sxs-lookup"><span data-stu-id="6f83e-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="6f83e-122">幸運的是，Q# 支援許多設計人員熟悉的傳統偵錯技術，以及屬於量子特有的偵錯技術。</span><span class="sxs-lookup"><span data-stu-id="6f83e-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="6f83e-123">其中包括在 Q# 中建立和執行單元測試、在程式碼中的值和機率內嵌*判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。</span><span class="sxs-lookup"><span data-stu-id="6f83e-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="6f83e-124">後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，[不複製定理](xref:microsoft.quantum.concepts.pauli))，以偵測計算的特定部分。</span><span class="sxs-lookup"><span data-stu-id="6f83e-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="6f83e-125">量子模擬器和資源估算器</span><span class="sxs-lookup"><span data-stu-id="6f83e-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="6f83e-126">[量子模擬器和主應用程式](xref:microsoft.quantum.machines)：概述可用的各種模擬器，以及主程式與目標機器如何共同運作，以執行 Q# 程式。</span><span class="sxs-lookup"><span data-stu-id="6f83e-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="6f83e-127">[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)：模擬完整量子狀態的目標機器。</span><span class="sxs-lookup"><span data-stu-id="6f83e-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="6f83e-128">適用於完整執行或偵錯規模較小的程式 (少於數十個量子位元)</span><span class="sxs-lookup"><span data-stu-id="6f83e-128">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="6f83e-129">[資源估算器](xref:microsoft.quantum.machines.resources-estimator)：估算在量子電腦上執行 Q# 作業指定執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="6f83e-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="6f83e-130">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：執行量子程式，而不實際模擬量子電腦的狀態，因此可以執行使用數千個量子位元的量子程式。</span><span class="sxs-lookup"><span data-stu-id="6f83e-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="6f83e-131">適用於在量子程式內進行傳統程式碼的偵錯，以及預估所需的資源。</span><span class="sxs-lookup"><span data-stu-id="6f83e-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="6f83e-132">[Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)：特殊用途的量子模擬器，可對數百萬個量子位元使用，但僅適用於具有一組有限量子作業 (X、CNOT 和多重受控 X) 的程式。</span><span class="sxs-lookup"><span data-stu-id="6f83e-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="6f83e-133">快速參考指南</span><span class="sxs-lookup"><span data-stu-id="6f83e-133">Quick Reference Pages</span></span>

- <span data-ttu-id="6f83e-134">[IQ#Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter Notebook 中的 IQ# 魔術命令快速參考頁面。</span><span class="sxs-lookup"><span data-stu-id="6f83e-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
