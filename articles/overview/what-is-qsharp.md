---
title: Q# 和 QDK 是什麼？
description: 了解 Q#，其既是由 Microsoft 所建立來開發量子電腦應用程式的程式設計語言，也是 Microsoft Quantum Development Kit 的重要元件
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906996"
---
# <a name="what-are-q-and-the-qdk"></a><span data-ttu-id="b4bae-103">Q# 和 QDK 是什麼？</span><span class="sxs-lookup"><span data-stu-id="b4bae-103">What are Q# and the QDK?</span></span>

<span data-ttu-id="b4bae-104">Q# 是一種程式設計語言，其具有專門設計的功能，可與量子運算搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b4bae-104">Q# is a programming language with features specifically designed for use with quantum computing.</span></span>
<span data-ttu-id="b4bae-105">其作為 Microsoft Quantum Development Kit (QDK) 的重要元件，可為量子程式設計人員提供一個架構，讓您能夠專注於處理演算法，而不必擔心量子電腦的閘道序列最佳化或實體實作等技術細節。</span><span class="sxs-lookup"><span data-stu-id="b4bae-105">As a key component of Microsoft's Quantum Development Kit (QDK), it provides quantum programmers a framework that allows you to focus on the algorithms without having to worry about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="b4bae-106">QDK 包含各式各樣的工具，可為開發人員提供一切所需，讓其能夠開始撰寫量子程式。</span><span class="sxs-lookup"><span data-stu-id="b4bae-106">The QDK comprises a wide range of tools which give developers everything they need to start writing quantum programs.</span></span>
<span data-ttu-id="b4bae-107">除了 Q# 語言，QDK 還包含：</span><span class="sxs-lookup"><span data-stu-id="b4bae-107">Alongside the Q# language, the QDK includes:</span></span>
* <span data-ttu-id="b4bae-108">「Q# 程式庫」  ，可讓開發人員立即做好準備，開始建立真實的量子應用程式</span><span class="sxs-lookup"><span data-stu-id="b4bae-108">the *Q# libraries*, which allow developers to hit the ground running and create real-world quantum applications today</span></span>
* <span data-ttu-id="b4bae-109">可供執行 Q# 程式的各種「目標機器」  。</span><span class="sxs-lookup"><span data-stu-id="b4bae-109">various *target machines* on which Q# programs can be run.</span></span> <span data-ttu-id="b4bae-110">這些機器包括適用於較大型量子程式的資源估算器和模擬器，以及行為如同無雜訊量子電腦的全狀態量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="b4bae-110">These include resource estimators and simulators for larger quantum programs, as well as a full-state quantum simulator, which behaves as a noise-free quantum computer.</span></span> <span data-ttu-id="b4bae-111">後者非常適合用來完善概念、針對程式進行偵錯，以及了解量子物理，但若要有效率，就必須用在量子位元相對較少的程式上。</span><span class="sxs-lookup"><span data-stu-id="b4bae-111">The latter is very useful for tinkering with ideas, debugging programs, and learning about quantum physics, but only efficient for programs with relatively few qubits.</span></span> <span data-ttu-id="b4bae-112">我們非常期待未來有一天能讓量子運算硬體成為目標機器。</span><span class="sxs-lookup"><span data-stu-id="b4bae-112">We're very much looking forward to making quantum computing hardware available as target machines in the future.</span></span>
* <span data-ttu-id="b4bae-113">可讓使用 Q# 變得盡可能順暢的「工具」  ，例如適用於 Visual Studio 和 VS Code 的擴充功能，以及可供與 Python 和 Jupyter Notebook 搭配使用的套件。</span><span class="sxs-lookup"><span data-stu-id="b4bae-113">*tools* for making work with Q# as seamless as possible, such as extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebooks.</span></span>
* <span data-ttu-id="b4bae-114">用來讓 Q# 與傳統主機語言 (例如 Python 和 C#) 配對的「API 文件」 </span><span class="sxs-lookup"><span data-stu-id="b4bae-114">*API documentation* for pairing Q# with classical host languages such as Python and C#</span></span>

<span data-ttu-id="b4bae-115">以 Microsoft Quantum Development Kit 開發的應用程式一般會包含兩個部分：</span><span class="sxs-lookup"><span data-stu-id="b4bae-115">Applications developed with Microsoft's Quantum Development Kit typically consist of two parts:</span></span>
1. <span data-ttu-id="b4bae-116">一或多個量子演算法，使用 Q# 量子程式設計語言所實作，並由傳統主機程式來叫用。</span><span class="sxs-lookup"><span data-stu-id="b4bae-116">One or more quantum algorithms, implemented using the Q# quantum programming language, and invoked by the classical host program.</span></span> <span data-ttu-id="b4bae-117">這些演算法會由下列項目組成：</span><span class="sxs-lookup"><span data-stu-id="b4bae-117">These consist of</span></span> 
    - <span data-ttu-id="b4bae-118">Q# 運算：含有量子運算的副程式，以及</span><span class="sxs-lookup"><span data-stu-id="b4bae-118">Q# operations: subroutines containing quantum operations, and</span></span> 
    - <span data-ttu-id="b4bae-119">Q# 函式：在量子演算法內使用的傳統副程式。</span><span class="sxs-lookup"><span data-stu-id="b4bae-119">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="b4bae-120">一個傳統程式，以傳統的程式設計語言 (例如 Python 或 C#) 來實作，既作為主要進入點，又會在想要執行量子演算法時叫用 Q# 運算。</span><span class="sxs-lookup"><span data-stu-id="b4bae-120">A classical program, implemented in a classical programming language like Python or C#, that serves as the main entry point and will invoke Q# operations when it wants to execute a quantum algorithm.</span></span>

## <a name="write-quantum-programs-not-quantum-circuits"></a><span data-ttu-id="b4bae-121">撰寫量子程式而非量子電路</span><span class="sxs-lookup"><span data-stu-id="b4bae-121">Write quantum programs, not quantum circuits</span></span>

<span data-ttu-id="b4bae-122">在量子運算初期，演算法是用類似古典運算中的電路圖來做出圖表化的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="b4bae-122">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>
<span data-ttu-id="b4bae-123">雖然電路模型長年來在量子運算研究領域發揮了良好成效，但 Microsoft 相信開發人員可以超越量子電路，而使用 Q# 來開發量子演算法和應用程式。</span><span class="sxs-lookup"><span data-stu-id="b4bae-123">While the circuit model has been useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span>
<span data-ttu-id="b4bae-124">建置 Q# 語言的目的，是要利用我們數十年來進行傳統軟體開發所獲得的成果，讓開發人員能夠使用針對量子運算而設計的高階語言功能。</span><span class="sxs-lookup"><span data-stu-id="b4bae-124">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality targeted for quantum computing.</span></span>

## <a name="how-does-q-work"></a><span data-ttu-id="b4bae-125">Q# 的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="b4bae-125">How does Q# work?</span></span>

<span data-ttu-id="b4bae-126">Q# 程式設計語言提供了一組直覺式的類型、作業和邏輯運算式來開發演算法，而您不需要顧慮量子電腦的內部邏輯。</span><span class="sxs-lookup"><span data-stu-id="b4bae-126">The Q# programming language provides you with an intuitive set of types, operations, and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

<span data-ttu-id="b4bae-127">Q# 的其中一個基本構成要素是 `Qubit` 類型，它無法複製或直接存取，就像實際的量子位元一樣。</span><span class="sxs-lookup"><span data-stu-id="b4bae-127">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span>
<span data-ttu-id="b4bae-128">不過，我們可加以測量，並將測量的結果儲存在 `Result` 變數中，這是可接受兩個可能值的 Q# 類型：`Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="b4bae-128">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span>
<span data-ttu-id="b4bae-129">這樣的結構可確保演算法一律會遵循量子物理的法則，並且可在量子電腦或模擬器上正確執行。</span><span class="sxs-lookup"><span data-stu-id="b4bae-129">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="b4bae-130">Q# 也包含傳統邏輯功能 (例如條件和迴圈)，並且藉由細微的差異確保能遵循所有量子規則。</span><span class="sxs-lookup"><span data-stu-id="b4bae-130">Q# also includes classical logic features like conditionals and loops with some subtleties to make sure that all the quantum rules are being respected.</span></span>
<span data-ttu-id="b4bae-131">例如，限制執行迴圈的方式，確保不會在只能包含確定性傳統子程式的函式中呼叫量子作業。</span><span class="sxs-lookup"><span data-stu-id="b4bae-131">For example, constraining the way loops are executed to ensure that quantum operations are not called within functions which may only contain deterministic classical subroutines.</span></span>

<span data-ttu-id="b4bae-132">Q# 程式通常會與以 C# 或 Python 撰寫的主機程式配對，這有助於組織傳統和量子程式碼。</span><span class="sxs-lookup"><span data-stu-id="b4bae-132">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span>
<span data-ttu-id="b4bae-133">除了支援 C# 和 Python 等語言以外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。</span><span class="sxs-lookup"><span data-stu-id="b4bae-133">In addition to supporting languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="what-can-i-use-q-for"></a><span data-ttu-id="b4bae-134">Q# 有哪些用途？</span><span class="sxs-lookup"><span data-stu-id="b4bae-134">What can I use Q# for?</span></span>

### <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="b4bae-135">使用 Q# 學習量子運算</span><span class="sxs-lookup"><span data-stu-id="b4bae-135">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="b4bae-136">目前，若要學習量子運算，您必須學習電路模型，以定序的量子閘道和測量的形式了解演算法。</span><span class="sxs-lookup"><span data-stu-id="b4bae-136">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="b4bae-137">透過 Q# 您將可採用另一個途徑：藉由撰寫量子程式來學習量子運算。</span><span class="sxs-lookup"><span data-stu-id="b4bae-137">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

### <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="b4bae-138">使用 Q# 設計量子演算法</span><span class="sxs-lookup"><span data-stu-id="b4bae-138">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="b4bae-139">Q# 可為您提供更多程式庫和使用者定義類型，以協助您實作工具來建置進階量子演算法。</span><span class="sxs-lookup"><span data-stu-id="b4bae-139">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="b4bae-140">例如，假設您需要讓兩個量子位元 q1 和 q2 相互糾纏。</span><span class="sxs-lookup"><span data-stu-id="b4bae-140">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="b4bae-141">您可以使用既有的內建作業 `PrepareEntangledState([q1], [q2])` 讓量子位元相互糾纏，而無須個別套用必要的閘道。</span><span class="sxs-lookup"><span data-stu-id="b4bae-141">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

### <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="b4bae-142">使用 Q# 來估計量子資源</span><span class="sxs-lookup"><span data-stu-id="b4bae-142">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="b4bae-143">您可以使用 Quantum Development Kit (QDK) 提供的全態量子模擬器，模擬您的 Q# 程式執行。</span><span class="sxs-lookup"><span data-stu-id="b4bae-143">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="b4bae-144">QDK 也提供資源估算器，讓您解析 Q # 程式效能，看出在模擬器上執行會太大的程式。</span><span class="sxs-lookup"><span data-stu-id="b4bae-144">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too large to be run on a simulator.</span></span>  <span data-ttu-id="b4bae-145">這對演算法設計人員來說非常重要，因為他們可以微調程式使其使用較少的資源 (例如，較少量子位元執行較少作業)，以利盡早在較小規模的量子硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="b4bae-145">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>

### <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="b4bae-146">使用 Q# 來驗證硬體效能</span><span class="sxs-lookup"><span data-stu-id="b4bae-146">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="b4bae-147">Q# 的優點是可以只撰寫程式一次，就在量子模擬器上執行並偵錯，並在不同量子電腦硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="b4bae-147">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on different quantum computer hardware.</span></span>  <span data-ttu-id="b4bae-148">您可以執行以 Q# 撰寫的基準測試程式來驗證硬體效能並比較結果，促成量子電腦的演進，和新量子電腦的問市。</span><span class="sxs-lookup"><span data-stu-id="b4bae-148">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="b4bae-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b4bae-149">Next steps</span></span>

* [<span data-ttu-id="b4bae-150">要如何學習量子運算？</span><span class="sxs-lookup"><span data-stu-id="b4bae-150">How do I learn about quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="b4bae-151">開始使用 Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="b4bae-151">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
