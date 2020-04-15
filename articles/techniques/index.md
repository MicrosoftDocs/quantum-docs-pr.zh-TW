---
title: Quantum 開發技術
description: 了解 Q# 程式開發的基本概念、使用作業、函式、變數和量子位元，以及建立簡單的量子程式。
keywords: 請勿在未諮詢 SEO 之前新增或編輯關鍵字。
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907710"
---
# <a name="quantum-development-techniques"></a><span data-ttu-id="d07b9-104">Quantum 開發技術</span><span class="sxs-lookup"><span data-stu-id="d07b9-104">Quantum Development Techniques</span></span>

<span data-ttu-id="d07b9-105">本文件的這個部分詳述所用的核心概念，讓您了解如何在 Q# 中建立量子程式以及從傳統應用程式與這些量子程式互動。</span><span class="sxs-lookup"><span data-stu-id="d07b9-105">This section of our documentation details the core concepts used to create quantum programs in Q#, and to interact with those programs from classical applications.</span></span>
<span data-ttu-id="d07b9-106">我們假設您對量子運算概念 (如[量子運算概念](xref:microsoft.quantum.concepts.intro)所述內容) 有*一些*了解，但您不需專精於量子運算，也能從這些章節獲益良多。</span><span class="sxs-lookup"><span data-stu-id="d07b9-106">We assume *some* knowledge of quantum computing concepts, like those described in [Quantum computing concepts](xref:microsoft.quantum.concepts.intro), but you need not be an expert in quantum computing to get a lot from these sections.</span></span>

<span data-ttu-id="d07b9-107">這個部分的內容如下。</span><span class="sxs-lookup"><span data-stu-id="d07b9-107">Their contents are as follows.</span></span>

- <span data-ttu-id="d07b9-108">[Q# 程式概觀](xref:microsoft.quantum.techniques.file-structure)提供 Q# 程式設計語言的用途和功能概述。</span><span class="sxs-lookup"><span data-stu-id="d07b9-108">[Q# program overview](xref:microsoft.quantum.techniques.file-structure) provides an overview of the purpose and functionality of the Q# programming language.</span></span> 
    <span data-ttu-id="d07b9-109">文中特別闡明 Q# *不*只是用來模擬量子機制的語言，儘管我們的完整狀態模擬器確實有這個功能。</span><span class="sxs-lookup"><span data-stu-id="d07b9-109">In particular, it clarifies how Q# is *not* a language for merely simulating quantum mechanics---though that functionality is of course provided by our full state simulator.</span></span> 
    <span data-ttu-id="d07b9-110">不如說 Q# 的設計是著眼於未來，其程式能描述傳統控制電腦如何與量子位元*互動*。</span><span class="sxs-lookup"><span data-stu-id="d07b9-110">Rather, Q# was designed with an eye on the future, and its programs describe how a classical control computer *interacts* with qubits.</span></span> 

- <span data-ttu-id="d07b9-111">[作業和函數](xref:microsoft.quantum.techniques.opsandfunctions)詳細說明 Q# 語言的兩種可呼叫類型：*作業*含括量子位元和量子系統上的動作，*函數*則嚴格地處理傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="d07b9-111">[Operations and functions](xref:microsoft.quantum.techniques.opsandfunctions) details the two callable types of the Q# language: *operations*, which include action on qubits and quantum systems; and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="d07b9-112">如果沒有傳統和量子資訊同時運作，量子運算仍遙不可及。</span><span class="sxs-lookup"><span data-stu-id="d07b9-112">Without both classical and quantum information working in tandem, quantum computing would remain out of reach.</span></span> 
    <span data-ttu-id="d07b9-113">本章節說明如何在 Q# 程式的控制流程中定義和使用這些可呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="d07b9-113">This section describes how to define and use these callables within the control flow of a Q# program.</span></span>

- <span data-ttu-id="d07b9-114">[區域變數](xref:microsoft.quantum.techniques.local-variables)描述 Q# 程式中變數的角色，以及如何有效地運用。</span><span class="sxs-lookup"><span data-stu-id="d07b9-114">[Local variables](xref:microsoft.quantum.techniques.local-variables) describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="d07b9-115">特別是，您將瞭解不可變/可變變數之間的差異，以及如何指派/重新指派。</span><span class="sxs-lookup"><span data-stu-id="d07b9-115">In particular, you will learn the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="d07b9-116">[使用量子位元](xref:microsoft.quantum.techniques.qubits)說明可以用來處理個別量子位元和量子位元系統的 Q# 功能。</span><span class="sxs-lookup"><span data-stu-id="d07b9-116">[Working with qubits](xref:microsoft.quantum.techniques.qubits) describes the features of Q# that you can use to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="d07b9-117">具體來說，這需要其配置、對其執行作業，最後對其測量。</span><span class="sxs-lookup"><span data-stu-id="d07b9-117">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 
    <span data-ttu-id="d07b9-118">此外，您還會學到一些實用的控制流程技術。</span><span class="sxs-lookup"><span data-stu-id="d07b9-118">Additionally, you will learn some useful control flow techniques.</span></span>

- <span data-ttu-id="d07b9-119">將其[全部放在一起](xref:microsoft.quantum.techniques.puttingittogether)，您將利用上述各章節中的技巧來建立程式，以執行**量子傳送**：使用兩個傳統位元來將量子位元的完整狀態「傳送」到另一個。</span><span class="sxs-lookup"><span data-stu-id="d07b9-119">In [Putting it all together](xref:microsoft.quantum.techniques.puttingittogether), you will leverage the techniques from the sections above to create a program which performs **quantum teleportation**: using two classical bits to "teleport" the full state of one qubit onto another.</span></span>

- <span data-ttu-id="d07b9-120">[更進一步](xref:microsoft.quantum.techniques.going-further)介紹先進的技術，當您涉足更複雜的量子程式設計時，這會很有幫助。</span><span class="sxs-lookup"><span data-stu-id="d07b9-120">[Going further](xref:microsoft.quantum.techniques.going-further) introduces advanced techniques that can prove helpful as you move toward more complex quantum programming.</span></span> 
    <span data-ttu-id="d07b9-121">特別是我們會討論在 Q# 中使用*類型參數化*的作業和函數，藉由保持與特定類型的輸入/輸出無關以及*借用*量子位元，達成更高順序的控制流程。</span><span class="sxs-lookup"><span data-stu-id="d07b9-121">In particular, we discuss the use of *type-parameterized* operations and functions in Q#, which enable higher-order control flow by remaining agnostic to the specific types of their input/output, as well as *borrowing* qubits.</span></span> 
    <span data-ttu-id="d07b9-122">後者與基本量子位元配置不同之處在於，Q# 作業可以使用「已變更」的量子位元 --- 量子位元不一定會初始化為已知狀態 --- 來協助計算。</span><span class="sxs-lookup"><span data-stu-id="d07b9-122">The latter differs from basic qubit allocation in that a Q# operation may use "dirty" qubits---qubits not necessarily initialized to a known state---to assist computations.</span></span>

- <span data-ttu-id="d07b9-123">[測試與偵錯](xref:microsoft.quantum.techniques.testing-and-debugging)詳細說明一些技術，用來確保您的程式碼會執行其作業。</span><span class="sxs-lookup"><span data-stu-id="d07b9-123">[Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="d07b9-124">由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。</span><span class="sxs-lookup"><span data-stu-id="d07b9-124">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="d07b9-125">幸運的是，Q# 支援許多設計人員慣用的傳統偵錯技術，以及屬於量子特有的偵錯技術。</span><span class="sxs-lookup"><span data-stu-id="d07b9-125">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="d07b9-126">其中包括在 Q# 中建立/執行單元測試、在程式碼中的值和機率內嵌*判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。</span><span class="sxs-lookup"><span data-stu-id="d07b9-126">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="d07b9-127">後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，不複製定理) 來偵錯計算的特定部分。</span><span class="sxs-lookup"><span data-stu-id="d07b9-127">The latter can be used alongside our full state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>


![Quantum](~/media/mobius_strip_preview.png)
