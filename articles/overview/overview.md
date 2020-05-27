---
title: 量子運算簡介
description: 了解量子運算是什麼、量子電腦的功用，以及如何學習量子運算。
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
ms.openlocfilehash: 7c55420bd35f9b6e0e7ec80ddffe8a861cb7df39
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430776"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a><span data-ttu-id="c905f-103">簡介量子運算和 Quantum 開發套件</span><span class="sxs-lookup"><span data-stu-id="c905f-103">Introduction to quantum computing and the Quantum Development Kit</span></span>

<span data-ttu-id="c905f-104">Microsoft Quantum 開發套件 (QDK) 是一組開放原始碼工具，專門設計來協助開發人員學習量子演算法和撰寫量子程式。</span><span class="sxs-lookup"><span data-stu-id="c905f-104">The Microsoft Quantum Development Kit (QDK) is a set of open-source tools designed to help developers learn quantum algorithms and write quantum programs.</span></span> <span data-ttu-id="c905f-105">量子運算有望解決地球上的某些最大挑戰：在環境、農業、健康、能源、氣候、材料科學等領域，以及我們尚未遇過的其他問題。</span><span class="sxs-lookup"><span data-stu-id="c905f-105">Quantum computing holds the promise to solve some of our planet's biggest challenges - in the areas of environment, agriculture, health, energy, climate, materials science, and others we haven't encountered yet.</span></span>  

<span data-ttu-id="c905f-106">針對這些問題，即使是功能最強大的電腦也會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="c905f-106">For some of these problems, even our most powerful computers run into problems.</span></span> <span data-ttu-id="c905f-107">雖然量子技術才剛剛開始影響運算世界，但其影響深遠，可能會改變我們對運算的想法。</span><span class="sxs-lookup"><span data-stu-id="c905f-107">While quantum technology is just beginning to impact the computing world, it could be far-reaching and change the way we think about computing.</span></span>

## <a name="what-is-quantum-computing"></a><span data-ttu-id="c905f-108">什麼是量子運算？</span><span class="sxs-lookup"><span data-stu-id="c905f-108">What is quantum computing?</span></span>

<span data-ttu-id="c905f-109">量子一詞在現代用法中代表的是任何物理特性的最小可能離散單位，通常是指原子或次原子粒子的特性。</span><span class="sxs-lookup"><span data-stu-id="c905f-109">In modern usage, the word quantum means the smallest possible discrete unit of any physical property, usually referring to properties of atomic or subatomic particles.</span></span> <span data-ttu-id="c905f-110">量子電腦會使用實際的量子粒子、人造原子或量子粒子的集體特性作為處理單位，算是大型、複數且昂貴的裝置。</span><span class="sxs-lookup"><span data-stu-id="c905f-110">Quantum computers use actual quantum particles, artificial atoms, or collective properties of quantum particles as processing units, and are large, complex, and expensive devices.</span></span>

<span data-ttu-id="c905f-111">利用量子物理的獨特行為，並將此行為運用到運算，量子電腦在傳統的程式設計方法中引進了新的概念，並且會善加利用疊加、糾纏和量子干涉等量子物理行為。</span><span class="sxs-lookup"><span data-stu-id="c905f-111">Harnessing the unique behavior of quantum physics and applying it to computing, quantum computers introduce new concepts to traditional programming methods, making use of quantum physics behaviors such as superposition, entanglement, and quantum interference.</span></span>

## <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="c905f-112">量子電腦有何功用？</span><span class="sxs-lookup"><span data-stu-id="c905f-112">What can a quantum computer do?</span></span>

<span data-ttu-id="c905f-113">量子電腦並非可以更快完成所有運算的超級電腦，但量子電腦會在幾個領域有更加出色的表現。</span><span class="sxs-lookup"><span data-stu-id="c905f-113">A quantum computer isn't a supercomputer that can do everything faster, but there are a few areas where quantum computers do exceptionally well.</span></span>

- [<span data-ttu-id="c905f-114">量子模擬</span><span class="sxs-lookup"><span data-stu-id="c905f-114">Quantum simulation</span></span>](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [<span data-ttu-id="c905f-115">碼編譯</span><span class="sxs-lookup"><span data-stu-id="c905f-115">Cryptography</span></span>](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [<span data-ttu-id="c905f-116">搜尋</span><span class="sxs-lookup"><span data-stu-id="c905f-116">Search</span></span>](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [<span data-ttu-id="c905f-117">最佳化</span><span class="sxs-lookup"><span data-stu-id="c905f-117">Optimization</span></span>](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [<span data-ttu-id="c905f-118">機器學習服務</span><span class="sxs-lookup"><span data-stu-id="c905f-118">Machine learning</span></span>](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a><span data-ttu-id="c905f-119">量子模擬</span><span class="sxs-lookup"><span data-stu-id="c905f-119">Quantum simulation</span></span>

<span data-ttu-id="c905f-120">由於量子電腦會在運算中使用量子現象，因此很適合用來建立其他量子系統的模型。</span><span class="sxs-lookup"><span data-stu-id="c905f-120">Since quantum computers use quantum phenomena in computation, they are well suited for modeling other quantum systems.</span></span> <span data-ttu-id="c905f-121">光合作用、超導體和複雜分子的構造皆是量子程式所能模擬的量子力學範例。</span><span class="sxs-lookup"><span data-stu-id="c905f-121">Photosynthesis, superconductivity, and complex molecular formations are examples of quantum mechanisms that quantum programs can simulate.</span></span>

## <a name="cryptography-and-shors-algorithm"></a><span data-ttu-id="c905f-122">加密和秀爾演算法</span><span class="sxs-lookup"><span data-stu-id="c905f-122">Cryptography and Shor’s algorithm</span></span>

<span data-ttu-id="c905f-123">西元 1994 年時，彼得‧秀爾展示了可擴縮的量子電腦，這種量子電腦可以破解廣泛使用的加密技術，例如 RSA 演算法。</span><span class="sxs-lookup"><span data-stu-id="c905f-123">In 1994, Peter Shor showed that a scalable quantum computer could break widely used encryption techniques such as the RSA algorithm.</span></span> <span data-ttu-id="c905f-124">傳統加密會仰賴不可駕馭的問題，例如整數分解或離散對數，但這些問題有許多都可以透過量子電腦更有效率地解決。</span><span class="sxs-lookup"><span data-stu-id="c905f-124">Classical cryptography relies on the intractability of problems such as integer factorization or discrete logarithms, many of which can be solved more efficiently using quantum computers.</span></span>

## <a name="search-and-grovers-algorithm"></a><span data-ttu-id="c905f-125">搜尋和格羅弗演算法</span><span class="sxs-lookup"><span data-stu-id="c905f-125">Search and Grover’s algorithm</span></span>

<span data-ttu-id="c905f-126">西元 1996 年時，洛夫‧格羅弗開發了一種量子演算法，以大幅加快非結構化資料搜尋的解決方案，而能透過比任何傳統演算法更少的步驟來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c905f-126">In 1996, Lov Grover developed a quantum algorithm that dramatically sped up the solution to unstructured data searches, running the search in fewer steps than any classical algorithm could.</span></span>

## <a name="quantum-inspired-computing-and-optimization"></a><span data-ttu-id="c905f-127">受量子啟發的運算與最佳化</span><span class="sxs-lookup"><span data-stu-id="c905f-127">Quantum-inspired computing and optimization</span></span>

<span data-ttu-id="c905f-128">受量子啟發的演算法會使用量子原理來提升速度和正確性，但實作對象卻是傳統的電腦系統。</span><span class="sxs-lookup"><span data-stu-id="c905f-128">Quantum-inspired algorithms use quantum principles for increased speed and accuracy but implement on classical computer systems.</span></span> <span data-ttu-id="c905f-129">這種方法可讓開發人員立即運用新量子技術的威力，而不必等待仍屬新興產業的量子硬體。</span><span class="sxs-lookup"><span data-stu-id="c905f-129">This approach allows developers to leverage the power of new quantum techniques today without waiting for quantum hardware, which is still an emerging industry.</span></span>

<span data-ttu-id="c905f-130">最佳化是指在指定其所需結果和條件約束的情況下找出問題最佳解決方案的過程。</span><span class="sxs-lookup"><span data-stu-id="c905f-130">Optimization is the process of finding the best solution to a problem, given its desired outcome and constraints.</span></span> <span data-ttu-id="c905f-131">成本、品質或生產時間等都是產業界和科學界在做出重要決定時的關鍵因素。</span><span class="sxs-lookup"><span data-stu-id="c905f-131">Factors such as cost, quality, or production time all play into critical decisions made by industry and science.</span></span> <span data-ttu-id="c905f-132">在現今的傳統電腦上執行受量子啟發的最佳化演算法，便可找到截至目前為止還不可行的解決方案。</span><span class="sxs-lookup"><span data-stu-id="c905f-132">Quantum-inspired optimization algorithms running on today's classical computers can find solutions that up to now have not been possible.</span></span> <span data-ttu-id="c905f-133">除了將交通流量最佳化以減少塞車情形，飛機閘門指派、包裹運送、工作排程等等也都能最佳化。</span><span class="sxs-lookup"><span data-stu-id="c905f-133">In addition to optimizing traffic flow to reduce congestion, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="c905f-134">由於材料科學的突破，將會有新形式的能源、更大容量的電池、更輕更耐用的材料問市。</span><span class="sxs-lookup"><span data-stu-id="c905f-134">With breakthroughs in materials science, there will be new forms of energy, batteries with larger capacity, and lighter and more durable materials.</span></span>

> [!NOTE]
> <span data-ttu-id="c905f-135">請深入了解 Microsoft 受量子啟發的運算如何運用在[材料科學](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[風險管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)和[藥物](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)上。</span><span class="sxs-lookup"><span data-stu-id="c905f-135">Read more about how Microsoft quantum-inspired computing is being used in [materials science](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [risk management](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/), and [medicine](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).</span></span>

## <a name="quantum-machine-learning"></a><span data-ttu-id="c905f-136">量子機器學習</span><span class="sxs-lookup"><span data-stu-id="c905f-136">Quantum machine learning</span></span>

<span data-ttu-id="c905f-137">傳統電腦上的機器學習革新了科學界和企業界。</span><span class="sxs-lookup"><span data-stu-id="c905f-137">Machine learning on classical computers is revolutionizing the world of science and business.</span></span> <span data-ttu-id="c905f-138">不過，由於將模型定型的運算成本高昂，因此會阻礙其發展和適用領域。</span><span class="sxs-lookup"><span data-stu-id="c905f-138">However, the high computational cost of training the models hinders the development and scope of the field.</span></span> <span data-ttu-id="c905f-139">量子機器學習的領域會探索如何設計和實作量子軟體，以便讓機器學習的執行速度快過傳統電腦。</span><span class="sxs-lookup"><span data-stu-id="c905f-139">The area of quantum machine learning explores how to devise and implement quantum software that enables machine learning that runs faster than classical computers.</span></span>

<span data-ttu-id="c905f-140">Quantum 開發套件隨附[量子機器學習程式庫](xref:microsoft.quantum.machine-learning.concepts.intro)，可讓您執行量子/傳統混合機器學習實驗。</span><span class="sxs-lookup"><span data-stu-id="c905f-140">The Quantum Development Kit comes with the [quantum machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro) that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="c905f-141">此程式庫包含範例和教學課程，並且會提供必要工具供您實作新的量子和傳統混合演算法 (以電路為中心的量子分類器)，以解決受監督的分類問題。</span><span class="sxs-lookup"><span data-stu-id="c905f-141">The library includes samples and tutorials, and provides the necessary tools to implement a new hybrid quantum–classical algorithm, the circuit-centric quantum classifier, to solve supervised classification problems.</span></span>

## <a name="q-and-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c905f-142">Q# 和 Microsoft Quantum 開發套件 (QDK)</span><span class="sxs-lookup"><span data-stu-id="c905f-142">Q# and the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c905f-143">Q# 是 Microsoft 的開放原始碼程式設計語言，可用來開發和執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="c905f-143">Q# is Microsoft's open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="c905f-144">這是 [QDK](https://docs.microsoft.com/quantum/) (適用於 Q# 的完整功能開發套件) 的一部分，您可與標準工具和語言搭配使用，以開發可在各種環境中執行的量子應用程式，包括內建的全狀態量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="c905f-144">It is part of the [QDK](https://docs.microsoft.com/quantum/), a full-featured development kit for Q# that you can use with standard tools and languages to develop quantum applications that you can run in various environments, including the built-in full-state quantum simulator.</span></span>

<span data-ttu-id="c905f-145">既有適用於 Visual Studio 和 VS Code 的擴充功能，也有可與 Python 和 Jupyter Notebook 搭配使用的套件。</span><span class="sxs-lookup"><span data-stu-id="c905f-145">There are extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebook.</span></span>

<span data-ttu-id="c905f-146">QDK 包含標準程式庫，以及專門的化學、機器學習和數值程式庫。</span><span class="sxs-lookup"><span data-stu-id="c905f-146">The QDK includes a standard library along with specialized chemistry, machine learning, and numerics libraries.</span></span>

<span data-ttu-id="c905f-147">文件中包含可讓您快速開始使用的 Q# 語言指南、教學課程和範例程式碼，並有豐富文章可協助您深入了解量子運算的概念。</span><span class="sxs-lookup"><span data-stu-id="c905f-147">The documentation includes a Q# language guide, tutorials, and sample code to get you started quickly, and rich articles to help you dive deeper into quantum computing concepts.</span></span>  

## <a name="microsoft-quantum-hardware-partners"></a><span data-ttu-id="c905f-148">Microsoft 量子硬體合作夥伴</span><span class="sxs-lookup"><span data-stu-id="c905f-148">Microsoft quantum hardware partners</span></span>

<span data-ttu-id="c905f-149">Microsoft 與各家量子硬體公司合作，讓開發人員能夠透過雲端存取量子硬體。</span><span class="sxs-lookup"><span data-stu-id="c905f-149">Microsoft is partnering with quantum hardware companies to provide developers with cloud access to quantum hardware.</span></span> <span data-ttu-id="c905f-150">利用 [Azure Quantum](https://azure.microsoft.com/services/quantum/) 平台和 Q# 語言，開發人員將能夠探索量子演算法，並在不同類型的量子硬體上執行其量子程式。</span><span class="sxs-lookup"><span data-stu-id="c905f-150">Leveraging the [Azure Quantum](https://azure.microsoft.com/services/quantum/) platform and the Q# language, developers will be able to explore quantum algorithms and run their quantum programs on different types of quantum hardware.</span></span>

<span data-ttu-id="c905f-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) 和 [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) 都使用**以離子阱為基礎的**處理器，可利用電場中捕獲的個別離子，至於 [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) 則使用超導電路。</span><span class="sxs-lookup"><span data-stu-id="c905f-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) and [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) both use **trapped ion-based** processors, utilizing individual ions trapped in an electronic field, whereas [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) uses superconducting circuits.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c905f-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c905f-152">Next steps</span></span>

<span data-ttu-id="c905f-153">[量子運算的重要概念](xref:microsoft.quantum.overview.understanding)
[快速入門](xref:microsoft.quantum.welcome)</span><span class="sxs-lookup"><span data-stu-id="c905f-153">[Key concepts for quantum computing](xref:microsoft.quantum.overview.understanding)
[Quickstarts](xref:microsoft.quantum.welcome)</span></span>