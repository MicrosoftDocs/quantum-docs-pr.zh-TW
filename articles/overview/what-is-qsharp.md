---
title: 什麼是 Q#？
description: 了解 Microsoft 為了開發量子電腦的應用程式而建立的程式設計語言 Q#
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443948"
---
# <a name="what-is-q"></a><span data-ttu-id="02cc9-103">什麼是 Q#？</span><span class="sxs-lookup"><span data-stu-id="02cc9-103">What is Q#?</span></span>

<span data-ttu-id="02cc9-104">Q# 是一種程式設計語言，具備量子運算方面的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="02cc9-104">Q# is a programming language with features that are special to quantum computing.</span></span> <span data-ttu-id="02cc9-105">Q# 可為量子程式設計人員提供一個架構，讓您能夠專注於演算法，而無須分神考量閘道序列最佳化或量子電腦的實體執行等技術細節。</span><span class="sxs-lookup"><span data-stu-id="02cc9-105">Q# provides quantum programmers a framework that allows you to focus on the algorithms without having to care about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="02cc9-106">Q# 程式設計語言提供了一組直覺式的類型、作業和邏輯運算式來開發演算法，而您不需要顧慮量子電腦的內部邏輯。</span><span class="sxs-lookup"><span data-stu-id="02cc9-106">The Q# programming language provides you with an intuitive set of types, operations and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

## <a name="code-algorithms"></a><span data-ttu-id="02cc9-107">程式碼演算法</span><span class="sxs-lookup"><span data-stu-id="02cc9-107">Code algorithms</span></span>

<span data-ttu-id="02cc9-108">在量子運算初期，演算法是用類似古典運算中的電路圖來做出圖表化的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="02cc9-108">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>  <span data-ttu-id="02cc9-109">雖然電路模型長年來在量子運算研究領域發揮了良好成效，但 Microsoft 相信開發人員可以超越量子電路，而使用 Q# 來開發量子演算法和應用程式。</span><span class="sxs-lookup"><span data-stu-id="02cc9-109">While the circuit model has been very useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span> <span data-ttu-id="02cc9-110">建置 Q# 語言的目的，是要利用我們數十年來進行傳統軟體開發所獲得的成果，讓開發人員能夠使用針對量子運算而設計的高階語言功能。</span><span class="sxs-lookup"><span data-stu-id="02cc9-110">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality specifically targeted for quantum computing.</span></span>


## <a name="how-does-q-work"></a><span data-ttu-id="02cc9-111">Q# 的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="02cc9-111">How does Q# work?</span></span>

<span data-ttu-id="02cc9-112">Q# 的其中一個基本構成要素是 `Qubit` 類型，它無法複製或直接存取，就像實際的量子位元一樣。</span><span class="sxs-lookup"><span data-stu-id="02cc9-112">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span> <span data-ttu-id="02cc9-113">不過，我們可加以測量，並將測量的結果儲存在 `Result` 變數中，這是可接受兩個可能值的 Q# 類型：`Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="02cc9-113">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span> <span data-ttu-id="02cc9-114">這樣的結構可確保演算法一律會遵循量子物理的法則，並且可在量子電腦或模擬器上正確執行。</span><span class="sxs-lookup"><span data-stu-id="02cc9-114">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="02cc9-115">Q# 也包含傳統邏輯功能 (例如條件或迴圈)，並且藉由細微的差異確保能遵循所有量子規則。</span><span class="sxs-lookup"><span data-stu-id="02cc9-115">Q# also includes classical logic features like conditionals or loops with some subtleties to make sure that all the quantum rules are being respected.</span></span> <span data-ttu-id="02cc9-116">例如，量子作業必須是可還原的。</span><span class="sxs-lookup"><span data-stu-id="02cc9-116">For example, quantum operations need to be reversible.</span></span> <span data-ttu-id="02cc9-117">因此，必須對迴圈的執行方式施加某些條件約束。</span><span class="sxs-lookup"><span data-stu-id="02cc9-117">This enforces some constraints on the way loops are executed.</span></span>

<span data-ttu-id="02cc9-118">Q# 程式通常會與以 C# 或 Python 撰寫的主機程式配對，這有助於組織傳統和量子程式碼。</span><span class="sxs-lookup"><span data-stu-id="02cc9-118">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span> <span data-ttu-id="02cc9-119">除了支援 .NET 語言 (例如 C# 和 Python) 以外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。</span><span class="sxs-lookup"><span data-stu-id="02cc9-119">In addition to supporting .NET languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="02cc9-120">使用 Q# 學習量子運算</span><span class="sxs-lookup"><span data-stu-id="02cc9-120">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="02cc9-121">目前，若要學習量子運算，您必須學習電路模型，以定序的量子閘道和測量的形式了解演算法。</span><span class="sxs-lookup"><span data-stu-id="02cc9-121">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="02cc9-122">透過 Q# 您將可採用另一個途徑：藉由撰寫量子程式來學習量子運算。</span><span class="sxs-lookup"><span data-stu-id="02cc9-122">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

## <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="02cc9-123">使用 Q# 設計量子演算法</span><span class="sxs-lookup"><span data-stu-id="02cc9-123">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="02cc9-124">Q# 可為您提供更多程式庫和使用者定義類型，以協助您實作工具來建置進階量子演算法。</span><span class="sxs-lookup"><span data-stu-id="02cc9-124">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="02cc9-125">例如，假設您需要讓兩個量子位元 q1 和 q2 相互糾纏。</span><span class="sxs-lookup"><span data-stu-id="02cc9-125">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="02cc9-126">您可以使用既有的內建作業 `PrepareEntangledState([q1], [q2])` 讓量子位元相互糾纏，而無須個別套用必要的閘道。</span><span class="sxs-lookup"><span data-stu-id="02cc9-126">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

## <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="02cc9-127">使用 Q# 來估計量子資源</span><span class="sxs-lookup"><span data-stu-id="02cc9-127">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="02cc9-128">您可以使用 Quantum Development Kit (QDK) 提供的全態量子模擬器，模擬您的 Q# 程式執行。</span><span class="sxs-lookup"><span data-stu-id="02cc9-128">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="02cc9-129">QDK 也提供資源估算器，讓您解析 Q # 程式效能，看出在模擬器上執行會太大的程式。</span><span class="sxs-lookup"><span data-stu-id="02cc9-129">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too big to be run on a simulator.</span></span>  <span data-ttu-id="02cc9-130">這對演算法設計人員來說非常重要，因為他們可以微調程式使其使用較少的資源 (例如，較少量子位元執行較少作業)，以利盡早在較小規模的量子硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="02cc9-130">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>   

## <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="02cc9-131">使用 Q# 來驗證硬體效能</span><span class="sxs-lookup"><span data-stu-id="02cc9-131">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="02cc9-132">Q# 的優點是可以只撰寫程式一次，就在量子模擬器上執行並偵錯，並在多個量子電腦硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="02cc9-132">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on multiple quantum computer hardware.</span></span>  <span data-ttu-id="02cc9-133">您可以執行以 Q# 撰寫的基準測試程式來驗證硬體效能並比較結果，促成量子電腦的演進，和新量子電腦的問市。</span><span class="sxs-lookup"><span data-stu-id="02cc9-133">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="02cc9-134">後續步驟</span><span class="sxs-lookup"><span data-stu-id="02cc9-134">Next steps</span></span>

* [<span data-ttu-id="02cc9-135">如何學習量子運算？</span><span class="sxs-lookup"><span data-stu-id="02cc9-135">How do I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="02cc9-136">開始使用 Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="02cc9-136">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
