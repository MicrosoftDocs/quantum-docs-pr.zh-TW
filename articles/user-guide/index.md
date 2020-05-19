---
title: Q# 使用者指南
description: 使用者指南的用途和內容概觀
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430606"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="247dd-103">Q# 使用者指南</span><span class="sxs-lookup"><span data-stu-id="247dd-103">The Q# User Guide</span></span>

<span data-ttu-id="247dd-104">歡迎使用 Q# 使用者指南！</span><span class="sxs-lookup"><span data-stu-id="247dd-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="247dd-105">在此，我們將詳細說明 Q# 語言的核心概念，以及撰寫量子程式所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="247dd-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="247dd-106">使用者指南內容</span><span class="sxs-lookup"><span data-stu-id="247dd-106">User Guide Contents</span></span>

- <span data-ttu-id="247dd-107">[Q# 基本概念](xref:microsoft.quantum.guide.basics)：Q# 程式設計語言的用途和功能概述。</span><span class="sxs-lookup"><span data-stu-id="247dd-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="247dd-108">Q# 語言</span><span class="sxs-lookup"><span data-stu-id="247dd-108">Q# Language</span></span>

- <span data-ttu-id="247dd-109">[Q# 中的類型](xref:microsoft.quantum.guide.types)：配置 Q# 類型模型，並描述用於指定和使用類型的語法。</span><span class="sxs-lookup"><span data-stu-id="247dd-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="247dd-110">[類型運算式](xref:microsoft.quantum.guide.expressions)：詳細說明如何指定、參考、結合和操作 Q# 中每個類型的值。</span><span class="sxs-lookup"><span data-stu-id="247dd-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="247dd-111">使用 Q#</span><span class="sxs-lookup"><span data-stu-id="247dd-111">Using Q#</span></span>

- <span data-ttu-id="247dd-112">[Q# 檔案結構](xref:microsoft.quantum.guide.filestructure)：描述 `*.qs` Q# 檔案的結構和語法。</span><span class="sxs-lookup"><span data-stu-id="247dd-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="247dd-113">[作業和函式](xref:microsoft.quantum.guide.operationsfunctions)詳細說明 Q# 語言的兩種可呼叫類型：「作業」含括量子位元暫存器上的動作，「函式」則嚴格地處理傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="247dd-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="247dd-114">在這裡，您會了解如何定義和呼叫這些類型，包括伴隨 (adjoint) 和受控的量子作業版本。</span><span class="sxs-lookup"><span data-stu-id="247dd-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="247dd-115">[變數](xref:microsoft.quantum.guide.variables)：描述 Q# 程式中變數的角色，以及如何有效地運用。</span><span class="sxs-lookup"><span data-stu-id="247dd-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="247dd-116">例如，您可以找到繫結範圍的相關資訊，以及不可變/可變變數之間的差異，以及如何指派/重新指派這些變數。</span><span class="sxs-lookup"><span data-stu-id="247dd-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="247dd-117">[使用量子位元](xref:microsoft.quantum.guide.qubits)：說明可以用來處理個別量子位元和量子位元系統的 Q# 功能。</span><span class="sxs-lookup"><span data-stu-id="247dd-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="247dd-118">具體來說，這需要其配置、對其執行作業，最後對其測量。</span><span class="sxs-lookup"><span data-stu-id="247dd-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="247dd-119">[控制流程](xref:microsoft.quantum.guide.controlflow)：詳細說明 Q# 中可用的程式設計控制流程模式，其中包括許多標準技術 (條件式執行、for 迴圈、while 迴圈等)，以及量子特有的「重複直到成功 (Repeat-Until-Success)」模式。</span><span class="sxs-lookup"><span data-stu-id="247dd-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="247dd-120">[測試與偵錯](xref:microsoft.quantum.guide.testingdebugging)：詳細說明一些技術，用來確保您的程式碼會執行其作業。</span><span class="sxs-lookup"><span data-stu-id="247dd-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="247dd-121">由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。</span><span class="sxs-lookup"><span data-stu-id="247dd-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="247dd-122">幸運的是，Q# 支援許多設計人員慣用的傳統偵錯技術，以及屬於量子特有的偵錯技術。</span><span class="sxs-lookup"><span data-stu-id="247dd-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="247dd-123">其中包括在 Q# 中建立/執行單元測試、在程式碼中的值和機率內嵌*判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。</span><span class="sxs-lookup"><span data-stu-id="247dd-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="247dd-124">後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，不複製定理) 來偵錯計算的特定部分。</span><span class="sxs-lookup"><span data-stu-id="247dd-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="247dd-125">量子模擬器和資源估算器</span><span class="sxs-lookup"><span data-stu-id="247dd-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="247dd-126">[量子模擬器和主應用程式](xref:microsoft.quantum.machines)：概述可用的各種模擬器，以及主程式與目標機器之間的一般執行模型。</span><span class="sxs-lookup"><span data-stu-id="247dd-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="247dd-127">[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)：模擬完整量子狀態的目標機器。</span><span class="sxs-lookup"><span data-stu-id="247dd-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="247dd-128">適用於完整執行或偵錯規模較小的程式 (少於數十個量子位元)</span><span class="sxs-lookup"><span data-stu-id="247dd-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="247dd-129">[資源估算器](xref:microsoft.quantum.machines.resources-estimator)：估算在量子電腦上執行 Q# 作業指定執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="247dd-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="247dd-130">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：執行量子程式，而不實際模擬量子電腦的狀態，因此可以執行使用數千個量子位元的量子程式。</span><span class="sxs-lookup"><span data-stu-id="247dd-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="247dd-131">適用於在量子程式內進行傳統程式碼的偵錯，以及預估所需的資源。</span><span class="sxs-lookup"><span data-stu-id="247dd-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="247dd-132">[Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)：特殊用途的量子模擬器，可對數百萬個量子位元使用，但僅適用於具有一組有限量子作業的程式 (也就是 X、CNOT 和多重受控 X)。</span><span class="sxs-lookup"><span data-stu-id="247dd-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="247dd-133">快速參考指南</span><span class="sxs-lookup"><span data-stu-id="247dd-133">Quick Reference Pages</span></span>

- <span data-ttu-id="247dd-134">[IQ# 魔術命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter Notebook 中的 IQ# 魔術命令快速參考頁面。</span><span class="sxs-lookup"><span data-stu-id="247dd-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
