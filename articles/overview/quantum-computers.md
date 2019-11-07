---
title: 量子電腦有何功用？
description: 了解量子運算的影響，從新穎的量子演算法，到在傳統電腦上執行、受量子啟發的演算法。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529940"
---
# <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="d91c2-103">量子電腦有何功用？</span><span class="sxs-lookup"><span data-stu-id="d91c2-103">What can a quantum computer do?</span></span>

<span data-ttu-id="d91c2-104">量子電腦有什麼功用是傳統電腦所無法做到的？</span><span class="sxs-lookup"><span data-stu-id="d91c2-104">What can we do with a quantum computer that can't be done with a classical one?</span></span>

<span data-ttu-id="d91c2-105">用目前的電腦來解決一些世界上最具挑戰性的問題，可能要耗費數十億年的時間，但量子電腦可能只要幾天、幾小時、甚至是幾分鐘就能完成。</span><span class="sxs-lookup"><span data-stu-id="d91c2-105">To solve some of the world's most challenging problems, where finding a solution would take current computers billions of years, a quantum computer could do so in days, hours, or even minutes.</span></span>

<span data-ttu-id="d91c2-106">量子運算可讓研究人員開發新的觸媒和材料、改善藥物配方、加速人工智慧的進展，並解答關於宇宙起源的基本問題。</span><span class="sxs-lookup"><span data-stu-id="d91c2-106">Quantum computing will enable researchers to develop new catalysts and materials, improve medicines, accelerate advances in artificial intelligence, and answer fundamental questions about the origins of our universe.</span></span>

## <a name="quantum-simulation"></a><span data-ttu-id="d91c2-107">量子模擬</span><span class="sxs-lookup"><span data-stu-id="d91c2-107">Quantum simulation</span></span>

<span data-ttu-id="d91c2-108">使用量子程式來建立量子系統本身的模型具有巨大的潛力，可能會讓您發掘更多見解在許多產業進行創新。</span><span class="sxs-lookup"><span data-stu-id="d91c2-108">Using quantum programs to model quantum systems themselves has vast potential for unlocking insights leading to innovations across many industries.</span></span> <span data-ttu-id="d91c2-109">舉例來說，光合作用、超導體和複雜分子便是可使用量子程式來模擬的量子系統。</span><span class="sxs-lookup"><span data-stu-id="d91c2-109">Photosynthesis, superconductors, and complex molecules are examples of quantum systems that can be simulated using quantum programs.</span></span>

<span data-ttu-id="d91c2-110">若要模擬根據量子力學法則來運轉的微觀系統，會耗用大量運算資源。</span><span class="sxs-lookup"><span data-stu-id="d91c2-110">Simulating microscopic systems that behave according to the laws of quantum mechanics is computationally expensive.</span></span> <span data-ttu-id="d91c2-111">我們必須考慮到所有可能的疊加狀態，而且狀態的數目會隨著系統的大小而以指數方式成長。</span><span class="sxs-lookup"><span data-stu-id="d91c2-111">We need to take into account all the possible states that can be in superposition and the number of states grows exponentially with the size of the system.</span></span> <span data-ttu-id="d91c2-112">在量子電腦中，我們不必建立系統所有狀態的模型。</span><span class="sxs-lookup"><span data-stu-id="d91c2-112">In a quantum computer, we don’t need to model all of the states of the system.</span></span> <span data-ttu-id="d91c2-113">相反地，我們會將所要模擬系統的量子狀態內嵌在電腦本身的量子位元中，並使用一組特定的量子閘來執行模擬。</span><span class="sxs-lookup"><span data-stu-id="d91c2-113">Instead, we embed the quantum state of the system that we want to simulate in the qubits of the computer itself, and run the simulation with a specific set of quantum gates.</span></span> <span data-ttu-id="d91c2-114">換句話說，我們會使用量子電腦來模擬量子系統。</span><span class="sxs-lookup"><span data-stu-id="d91c2-114">In other words, we use a quantum computer to simulate a quantum system.</span></span>

<span data-ttu-id="d91c2-115">化學分子屬於量子系統，因此可透過這種方式進行分析。</span><span class="sxs-lookup"><span data-stu-id="d91c2-115">Chemical molecules are quantum systems and therefore can be analyzed in this way.</span></span> <span data-ttu-id="d91c2-116">這類化學製品的其中一例就是「固氮酶」  酵素，如果我們能更加了解其特性，就有可能降低當今肥料所消耗的能源和排放的溫室氣體。</span><span class="sxs-lookup"><span data-stu-id="d91c2-116">One such specific chemical is the _nitrogenase_ enzyme, which, with a better understanding of its properties, could have the potential to reduce the energy consumption and greenhouse gas emission of current fertilizers.</span></span>

## <a name="cryptography"></a><span data-ttu-id="d91c2-117">加密</span><span class="sxs-lookup"><span data-stu-id="d91c2-117">Cryptography</span></span>

<span data-ttu-id="d91c2-118">量子電腦最著名的應用可能是在密碼學，1994 年 Peter Shor 證明可擴充的量子電腦可以破壞所有廣泛使用的加密技術。</span><span class="sxs-lookup"><span data-stu-id="d91c2-118">Perhaps the most famous application of quantum computers is in cryptography, where Peter Shor showed in 1994 that a scalable quantum computer can break every widely used encryption technique.</span></span>  <span data-ttu-id="d91c2-119">傳統密碼學仰賴的是運算巨大數字極其困難的特性，例如將巨大數字因數分解為兩個質數。</span><span class="sxs-lookup"><span data-stu-id="d91c2-119">Classical cryptography relies on the intractability of operations on large numbers, such as factorization of large numbers into two prime numbers.</span></span>

<span data-ttu-id="d91c2-120">理論上，量子運算讓這些運算變得非常簡單 (透過 Shor 演算法)。</span><span class="sxs-lookup"><span data-stu-id="d91c2-120">Quantum computing makes these operations theoretically tractable (via Shor's algorithm).</span></span> <span data-ttu-id="d91c2-121">雖然目前的量子硬體規模實際上還無法實作此演算法，但目前已大量開發出抗量子演算法而能保證未來的資料安全性，包括用於加密和密碼編譯金鑰散發的新穎量子演算法。</span><span class="sxs-lookup"><span data-stu-id="d91c2-121">Whilst implementation of this algorithm is not physically possible with the current scale of quantum hardware, it has spawned development of quantum-resistant algorithms to future-proof data security, including novel quantum algorithms for encryption and cryptographic key distribution.</span></span>

<span data-ttu-id="d91c2-122">在 Microsoft，我們有領先全球的量子後密碼學和安全性開發量子抵抗演算法團隊。</span><span class="sxs-lookup"><span data-stu-id="d91c2-122">Here at Microsoft, we have the world's leading team in post-quantum cryptography and security developing quantum-resistant algorithms.</span></span>

## <a name="optimization"></a><span data-ttu-id="d91c2-123">最佳化</span><span class="sxs-lookup"><span data-stu-id="d91c2-123">Optimization</span></span>

<span data-ttu-id="d91c2-124">最佳化是針對高維度空間執行大型搜尋的工作，適用於指定最低代價函數的解決方案。</span><span class="sxs-lookup"><span data-stu-id="d91c2-124">Optimization is the task of performing a large search over a high-dimensional space for a solution that minimizes a given cost function.</span></span>   <span data-ttu-id="d91c2-125">在量子電腦上，我們可以加速演算法的最佳化過程，以利尋找其他方法不可能達成的解決方案。</span><span class="sxs-lookup"><span data-stu-id="d91c2-125">On a quantum computer, we can speed up optimization algorithms, enabling finding solutions that otherwise were not possible.</span></span> <span data-ttu-id="d91c2-126">應用範圍從運輸物流、醫療保健，到診斷、材料科學等。</span><span class="sxs-lookup"><span data-stu-id="d91c2-126">Applications range from transportation and logistics, healthcare, diagnostics, and material science.</span></span> <span data-ttu-id="d91c2-127">對於這些產業可能的效率提升有深遠的影響。</span><span class="sxs-lookup"><span data-stu-id="d91c2-127">There can be a profound impact on how these industries can become more efficient.</span></span>

<span data-ttu-id="d91c2-128">透過量子運算實行的最佳化可讓我們以現今傳統系統不可行的方式，在運輸和物流上突破創新。</span><span class="sxs-lookup"><span data-stu-id="d91c2-128">Optimization with quantum computing allows us to innovate around transportation and logistics in a way that is not possible with today’s classical systems.</span></span>

<span data-ttu-id="d91c2-129">最佳化的交通流量可以降低擁塞。</span><span class="sxs-lookup"><span data-stu-id="d91c2-129">Optimizing traffic flow can reduce congestion.</span></span>  <span data-ttu-id="d91c2-130">除了路線規劃，還有飛機登機門指派、包裹遞送、工作排程等等。</span><span class="sxs-lookup"><span data-stu-id="d91c2-130">In addition to route planning, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="d91c2-131">而材料科學上的突破，將會有新形式的能源、更高容量的電池、更輕更強韌的材料問市。</span><span class="sxs-lookup"><span data-stu-id="d91c2-131">With breakthroughs in materials science, there will be new forms of energy, batteries with greater capacity, lighter and stronger materials.</span></span>

## <a name="machine-learning"></a><span data-ttu-id="d91c2-132">機器學習服務</span><span class="sxs-lookup"><span data-stu-id="d91c2-132">Machine learning</span></span>

<span data-ttu-id="d91c2-133">傳統運算上的大量數值計算主要用於解決線性方程式系統，在機器學習的領域中尤其如此，其中大部分的運算成本都用在計算大型矩陣的反矩陣。</span><span class="sxs-lookup"><span data-stu-id="d91c2-133">A great number of numerical calculations on classical computing consist mainly in solving linear systems of equations, especially true in the field of machine learning where most of the computation cost goes into calculating the inverse of huge matrices.</span></span>

<span data-ttu-id="d91c2-134">幸運的是，有一個量子演算法可讓我們以比傳統電腦還要快的速度 (近乎指數) 來解出此系統。</span><span class="sxs-lookup"><span data-stu-id="d91c2-134">Fortunately, there is a quantum algorithm that allows us to approximately solve the system exponentially faster than a classical computer.</span></span> <span data-ttu-id="d91c2-135">對於每個需要求解線性方程式系統的問題，此演算法無疑開啟了大幅加速的大門。</span><span class="sxs-lookup"><span data-stu-id="d91c2-135">The algorithm opens the door to great speedups in every problem that needs the solution to linear systems of equations.</span></span>

<span data-ttu-id="d91c2-136">這些領域中的問題解決方案將有助於解決能源危機、氣候變遷、糧食不足、個人精確醫療診斷。</span><span class="sxs-lookup"><span data-stu-id="d91c2-136">Solutions to problems in these areas will help address the energy crisis, climate change, food scarcity, and personal and precise medical diagnosis.</span></span>

## <a name="quantum-inspired-computing"></a><span data-ttu-id="d91c2-137">受量子啟發的運算</span><span class="sxs-lookup"><span data-stu-id="d91c2-137">Quantum-inspired computing</span></span>

<span data-ttu-id="d91c2-138">使用傳統軟體來實作受量子啟發的演算法，但使用量子原理來提高速度和正確性。</span><span class="sxs-lookup"><span data-stu-id="d91c2-138">Quantum-inspired algorithms are implemented with classical software, but use quantum principles for increased speed and accuracy.</span></span>

<span data-ttu-id="d91c2-139">受量子啟發的演算法正實施到醫療研究當中。</span><span class="sxs-lookup"><span data-stu-id="d91c2-139">Quantum-inspired algorithms are being applied to medical research.</span></span> <span data-ttu-id="d91c2-140">例如，為了改善磁共振成像 (MRI) 掃描的正確度。</span><span class="sxs-lookup"><span data-stu-id="d91c2-140">For example, to improve the accuracy of Magnetic Resonance Imaging (MRI) scans.</span></span> <span data-ttu-id="d91c2-141">受量子啟發的運算則會用來將 MRI 機器的設定最佳化，以識別特定疾病。</span><span class="sxs-lookup"><span data-stu-id="d91c2-141">Quantum-inspired computing is being used to optimize the configuration of the MRI machines for identification of specific diseases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d91c2-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d91c2-142">Next steps</span></span>

* [<span data-ttu-id="d91c2-143">為何要學習量子運算？</span><span class="sxs-lookup"><span data-stu-id="d91c2-143">Why should I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.why)
* [<span data-ttu-id="d91c2-144">開始使用 Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="d91c2-144">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
