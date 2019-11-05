---
title: 如何使用 Q# 學習量子運算？
description: ''
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 8967fee11931c6cef4b2d98084b2e319cea55284
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444101"
---
# <a name="how-to-learn-quantum-computing"></a><span data-ttu-id="a06e3-102">如何學習量子運算？</span><span class="sxs-lookup"><span data-stu-id="a06e3-102">How to learn quantum computing?</span></span>

<span data-ttu-id="a06e3-103">取得指引以學習量子運算並編寫第一個程式。</span><span class="sxs-lookup"><span data-stu-id="a06e3-103">Get guidance for learning about quantum computing and writing your first programs.</span></span> <span data-ttu-id="a06e3-104">本指南並不詳盡，僅供作為入門之用。</span><span class="sxs-lookup"><span data-stu-id="a06e3-104">This isn't an exhaustive guide, but rather a good place to start.</span></span>

## <a name="getting-started-overview"></a><span data-ttu-id="a06e3-105">使用者入門概觀</span><span class="sxs-lookup"><span data-stu-id="a06e3-105">Getting Started overview</span></span>

<span data-ttu-id="a06e3-106">[開始使用 Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) 提供使用 Q# 進行量子運算的高階概觀，包括撰寫第一個 Q# 程式的教學課程、快速入門指南，以及適於開發量子程式的 Q# 量子程式庫簡介。</span><span class="sxs-lookup"><span data-stu-id="a06e3-106">[Get started with the Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) provides a high-level overview of quantum computing with Q#, including tutorials for writing your first Q# program, getting started guides and and introduction to the Q# quantum libraries for developing quantum programs.</span></span>

## <a name="learning-the-basics-what-do-you-need-to-know"></a><span data-ttu-id="a06e3-107">學習基本概念：您需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="a06e3-107">Learning the basics: what do you need to know?</span></span>

<span data-ttu-id="a06e3-108">您不需要知道量子物理就能學習 Q# 和量子運算，也可以開始編寫量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="a06e3-108">You don’t need to know quantum physics to learn about Q# and quantum computing or start writing quantum applications.</span></span>

<span data-ttu-id="a06e3-109">這些概念可讓您深入了解所需的基本知識，以便您可以開始編寫量子程式。</span><span class="sxs-lookup"><span data-stu-id="a06e3-109">These concepts will give you a good introduction to the fundamental knowledge you need to start coding quantum programs.</span></span>  

* <span data-ttu-id="a06e3-110">[基本的量子力學](xref:microsoft.quantum.concepts.intro)：我們說過，就算不知道量子物理也能開始編碼 (實際上也確實如此！)。</span><span class="sxs-lookup"><span data-stu-id="a06e3-110">[Basic quantum mechanics](xref:microsoft.quantum.concepts.intro): We just said that you don’t need to know quantum physics to start coding (and it’s true!).</span></span> <span data-ttu-id="a06e3-111">但如果對量子力學和其數學符號有一些基本概念，將有助於您了解量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="a06e3-111">But some basic concepts of quantum mechanics and its mathematical notation will be helpful to understand quantum programming.</span></span>

* <span data-ttu-id="a06e3-112">**線性代數 (向量和矩陣)** ：在量子運算中，量子態會以向量表示，並以線性轉換的方式對這些向量實施量子操作。</span><span class="sxs-lookup"><span data-stu-id="a06e3-112">**Linear algebra (vectors and matrices)**: In quantum computing, quantum states are represented by vectors, with quantum operations being linear transformations applied to these vectors.</span></span>  <span data-ttu-id="a06e3-113">這裡有[有關線性代數的 Jupyter Notebook 教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)。</span><span class="sxs-lookup"><span data-stu-id="a06e3-113">Here is a [Jupyter notebook tutorial on Linear Algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).</span></span>  <span data-ttu-id="a06e3-114">您也可以在我們的概念指南中，閱讀有關[向量和矩陣](xref:microsoft.quantum.concepts.vectors)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a06e3-114">You can also read more about this in our concept guide about [vectors and matrices](xref:microsoft.quantum.concepts.vectors).</span></span>

* <span data-ttu-id="a06e3-115">**複雜算術**：量子態向量的係數為複數。</span><span class="sxs-lookup"><span data-stu-id="a06e3-115">**Complex arithmetic**: The coefficients of quantum state vectors are complex numbers.</span></span> <span data-ttu-id="a06e3-116">即使不懂複數，您也可以了解一些基本的量子運算概念，但若要更深入地運用，您就必須在量子工具組中納入複數。</span><span class="sxs-lookup"><span data-stu-id="a06e3-116">You can understand some basic quantum computing concepts without them, but you won't get far before you need to incorporate them into your quantum toolkit.</span></span>  <span data-ttu-id="a06e3-117">這裡有[有關複雜算術的 Jupyter Notebook 教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)，其中說明處理量子運算所需的一些數學背景。</span><span class="sxs-lookup"><span data-stu-id="a06e3-117">Here is a [Jupyter notebook tutorial on complex arithmetic](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic) that explains some of the mathematical background required to work with quantum computing.</span></span> 

<span data-ttu-id="a06e3-118">現在您已具備基本概念，可以開始學習撰寫量子程式。</span><span class="sxs-lookup"><span data-stu-id="a06e3-118">Now that you have the basics, you're ready to start learning how to write quantum programs.</span></span>  <span data-ttu-id="a06e3-119">有幾個不同的做法：</span><span class="sxs-lookup"><span data-stu-id="a06e3-119">There are many ways to proceed:</span></span>

## <a name="do-the-quantum-katas"></a><span data-ttu-id="a06e3-120">使用 Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="a06e3-120">Do the Quantum Katas</span></span>

<span data-ttu-id="a06e3-121">[Quantum Katas](xref:microsoft.quantum.overview.katas) 是我們一系列開放原始碼形式的自學型教學課程，目標是要同時讓您學會量子運算和 Q# 程式設計的要素。</span><span class="sxs-lookup"><span data-stu-id="a06e3-121">The [Quantum Katas](xref:microsoft.quantum.overview.katas) are our open source series of self-paced tutorials aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span>  <span data-ttu-id="a06e3-122">每個 Kata 都會參考其他學習材料，您可以用來學習成功完成 Katas 所需的量子運算概念。</span><span class="sxs-lookup"><span data-stu-id="a06e3-122">Each kata references additional learning materials you can use to learn the quantum computing concepts needed to successfully complete the katas.</span></span>  

## <a name="dive-into-the-theory"></a><span data-ttu-id="a06e3-123">深入了解理論</span><span class="sxs-lookup"><span data-stu-id="a06e3-123">Dive into the theory</span></span>

<span data-ttu-id="a06e3-124">您可能會想要深入了解量子力學和量子運算的理論。</span><span class="sxs-lookup"><span data-stu-id="a06e3-124">Maybe you want to take a deeper look into the theory of quantum mechanics and quantum computing.</span></span> <span data-ttu-id="a06e3-125">這裡有一份實用資料的清單：</span><span class="sxs-lookup"><span data-stu-id="a06e3-125">Here you have a list of useful material:</span></span>

* <span data-ttu-id="a06e3-126">從我們的[量子運算概念](xref:microsoft.quantum.concepts.intro)指南來開始，裡面彙編了量子運算的基本概念。</span><span class="sxs-lookup"><span data-stu-id="a06e3-126">Start with our guide to [quantum computing concepts](xref:microsoft.quantum.concepts.intro), a compilation of basic concepts for quantum computing.</span></span>
* <span data-ttu-id="a06e3-127">「使用 Python 和 Q# 學習量子運算」  (Sarah C. Kaiser 和 Christopher E. Granade) 為幾乎不懂量子力學、但有一些程式設計背景的人提供了出色的簡介。</span><span class="sxs-lookup"><span data-stu-id="a06e3-127">_Learn Quantum Computing with Python and Q#_ (Sarah C. Kaiser and Christopher E. Granade) provides an excellent introduction for people who have little to no experience with quantum mechanics, but some programming background.</span></span>
* <span data-ttu-id="a06e3-128">「量子運算和量子資訊」  (Michael A. Nielsen, Isaac L. Chuang) 是量子運算領域中最常被引用的教科書。</span><span class="sxs-lookup"><span data-stu-id="a06e3-128">_Quantum Computation and Quantum Information_ (Michael A. Nielsen, Isaac L. Chuang) is the most cited text in the field of quantum computation.</span></span> <span data-ttu-id="a06e3-129">相關人士將其視為這方面主題的標準教科書。</span><span class="sxs-lookup"><span data-stu-id="a06e3-129">It is regarded as the standard text on the subject.</span></span> <span data-ttu-id="a06e3-130">本書假設讀者先前只懂一點量子力學和電腦科學。</span><span class="sxs-lookup"><span data-stu-id="a06e3-130">The book assumes minimal prior experience with quantum mechanics and computer science.</span></span> <span data-ttu-id="a06e3-131">對於想要對此主題有嚴謹認識的讀者，以及正在尋找參考資料以獲得進階概念的讀者來說，本書是很好的選擇。</span><span class="sxs-lookup"><span data-stu-id="a06e3-131">It is an excellent choice for those readers who want a rigorous introduction to the topic as well as for those who are looking for references for advanced concepts.</span></span>
* <span data-ttu-id="a06e3-132">MIT OpenCourseWare 有優秀的[線上課程](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr)，授課者是 Allan Adams，您可從中學到量子力學的基礎知識。</span><span class="sxs-lookup"><span data-stu-id="a06e3-132">MIT OpenCourseWare has an excellent [online course](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) imparted by Allan Adams for learning the basics of quantum mechanics.</span></span> <span data-ttu-id="a06e3-133">適合想要進一步了解基礎物理學的讀者。</span><span class="sxs-lookup"><span data-stu-id="a06e3-133">Perfect for those who want a better understanding of the underlying physics.</span></span>

## <a name="join-the-quantum-community"></a><span data-ttu-id="a06e3-134">加入量子社群</span><span class="sxs-lookup"><span data-stu-id="a06e3-134">Join the quantum community</span></span>

<span data-ttu-id="a06e3-135">您不必獨自學習，有一大群愛好者和專家會樂意幫忙。</span><span class="sxs-lookup"><span data-stu-id="a06e3-135">You don’t have to learn this alone, there is a big community of amateurs and experts alike who are willing to help you.</span></span> <span data-ttu-id="a06e3-136">不要害怕提出問題！</span><span class="sxs-lookup"><span data-stu-id="a06e3-136">Don’t be afraid to ask!</span></span>

* <span data-ttu-id="a06e3-137">如果您有任何關於 Q# 或量子運算的問題，請不要遲疑，立即探訪量子運算 StackExchange 網站。</span><span class="sxs-lookup"><span data-stu-id="a06e3-137">If you have any questions about Q# or quantum computing don’t hesitate and take a look at the Quantum Computing StackExchange site.</span></span> <span data-ttu-id="a06e3-138">如果在其中找不到您的具體問題，請隨時發問新的問題。</span><span class="sxs-lookup"><span data-stu-id="a06e3-138">If you don’t find your specific question you can always ask a new one.</span></span> 
* <span data-ttu-id="a06e3-139">造訪 [Q# 部落格](https://devblogs.microsoft.com/qsharp/)和 [Microsoft Quantum 部落格](https://cloudblogs.microsoft.com/quantum/)，隨時了解有關 Q# 的最新消息和資源。</span><span class="sxs-lookup"><span data-stu-id="a06e3-139">Check out [Q# blog](https://devblogs.microsoft.com/qsharp/) and [Microsoft Quantum Blog](https://cloudblogs.microsoft.com/quantum/) to stay up to date with the latest news and resources about Q#.</span></span>
* <span data-ttu-id="a06e3-140">造訪 [Q# 社群](https://qsharp.community/)和 [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp)，以尋找更多資源和資料。</span><span class="sxs-lookup"><span data-stu-id="a06e3-140">Check [Q# Community](https://qsharp.community/) and [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp) to look for more resources and material.</span></span>

 <span data-ttu-id="a06e3-141">如果您想要教授關於量子運算的課程，[Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) 可以協助提供課程協助。</span><span class="sxs-lookup"><span data-stu-id="a06e3-141">If you’re looking to teach a course on quantum computing, the [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) can help provide curriculum assistance.</span></span>  

