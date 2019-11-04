---
title: Q# 程式設計語言 | Microsoft Docs
description: Q# 程式設計語言
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442482"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="3a24d-103">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="3a24d-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="3a24d-104">簡介</span><span class="sxs-lookup"><span data-stu-id="3a24d-104">Introduction</span></span>

<span data-ttu-id="3a24d-105">量子運算的自然模型是將量子電腦視為副處理器，類似於 GPU、FPGA 和其他附屬處理器所使用的模型。</span><span class="sxs-lookup"><span data-stu-id="3a24d-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="3a24d-106">主要控制邏輯會在傳統「主機」電腦上執行傳統程式碼。</span><span class="sxs-lookup"><span data-stu-id="3a24d-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="3a24d-107">若適當且必要，主機程式便可叫用會在附屬處理器上執行的副程式。</span><span class="sxs-lookup"><span data-stu-id="3a24d-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="3a24d-108">當副程式完成時，主機程式便會存取副程式的結果。</span><span class="sxs-lookup"><span data-stu-id="3a24d-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="3a24d-109">Q# (Q-sharp) 是用來表示量子演算法的領域專屬程式設計語言。</span><span class="sxs-lookup"><span data-stu-id="3a24d-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="3a24d-110">其可在傳統主機程式和電腦的控制下，用來編寫會在附屬量子處理器上執行的副程式。</span><span class="sxs-lookup"><span data-stu-id="3a24d-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="3a24d-111">在量子處理器可供廣泛使用之前，Q# 副程式會在模擬器上執行。</span><span class="sxs-lookup"><span data-stu-id="3a24d-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="3a24d-112">Q# 提供了一組小型的基本類型，以及兩種方式 (陣列和元組) 來建立新的結構化類型。</span><span class="sxs-lookup"><span data-stu-id="3a24d-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="3a24d-113">其支援基本程序模型，可供使用迴圈和 if/then 陳述式來編寫程式。</span><span class="sxs-lookup"><span data-stu-id="3a24d-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="3a24d-114">Q# 中的最上層建構是使用者定義的類型、操作和函式。</span><span class="sxs-lookup"><span data-stu-id="3a24d-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="3a24d-115">下列各節會詳細說明：</span><span class="sxs-lookup"><span data-stu-id="3a24d-115">The following sections detail:</span></span>
- [<span data-ttu-id="3a24d-116">類型模型</span><span class="sxs-lookup"><span data-stu-id="3a24d-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="3a24d-117">運算式</span><span class="sxs-lookup"><span data-stu-id="3a24d-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="3a24d-118">陳述式</span><span class="sxs-lookup"><span data-stu-id="3a24d-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="3a24d-119">檔案結構</span><span class="sxs-lookup"><span data-stu-id="3a24d-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="3a24d-120">慣例</span><span class="sxs-lookup"><span data-stu-id="3a24d-120">Conventions</span></span>

<span data-ttu-id="3a24d-121">我們努力在確保所有情況下都會一致地使用常見標點符號。</span><span class="sxs-lookup"><span data-stu-id="3a24d-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="3a24d-122">我們希望這麼做能夠讓您更容易學習和閱讀 Q#，因為這些標點符號永遠會代表相同的東西，而且相同的概念永遠會以相同的方式來表示。</span><span class="sxs-lookup"><span data-stu-id="3a24d-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="3a24d-123">具體而言：</span><span class="sxs-lookup"><span data-stu-id="3a24d-123">Specifically:</span></span>

- <span data-ttu-id="3a24d-124">分號 (`;`)，用來結束陳述式或單行指示詞。</span><span class="sxs-lookup"><span data-stu-id="3a24d-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="3a24d-125">分號不會用於其他用途。</span><span class="sxs-lookup"><span data-stu-id="3a24d-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="3a24d-126">逗號 (`,`)，用來分隔序列的元素。</span><span class="sxs-lookup"><span data-stu-id="3a24d-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="3a24d-127">逗號會用於元組常值、陣列常值、引數清單、元組定義和類型清單。</span><span class="sxs-lookup"><span data-stu-id="3a24d-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="3a24d-128">**和舊版不同的是，不再支援以 `;` 作為陣列常值分隔符號。**</span><span class="sxs-lookup"><span data-stu-id="3a24d-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="3a24d-129">冒號 (`:`)，用來引入類型註釋。</span><span class="sxs-lookup"><span data-stu-id="3a24d-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="3a24d-130">冒號主要用在可呼叫的簽章中。</span><span class="sxs-lookup"><span data-stu-id="3a24d-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="3a24d-131">因為冒號一律會引進類型簽章，所以在 0.3 中引進的三元條件運算子會使用分隔號 (`|`) 來分隔 true 和 false 值；因此，Q# 會使用 `cond ? tval | fval` (而不是冒號) 來作為 C 中的分隔符號。</span><span class="sxs-lookup"><span data-stu-id="3a24d-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
