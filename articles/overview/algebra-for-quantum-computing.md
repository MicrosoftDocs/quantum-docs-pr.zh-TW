---
title: 量子計算的線性代數
description: 了解要對量子運算有所認識所需要的基本線性代數概念
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: bff1da475f87278bc9e769805b3fe0fe8704d47a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835123"
---
# <a name="linear-algebra-for-quantum-computing"></a><span data-ttu-id="78c93-103">量子計算的線性代數</span><span class="sxs-lookup"><span data-stu-id="78c93-103">Linear algebra for quantum computing</span></span>

<span data-ttu-id="78c93-104">線性代數是量子運算的語言。</span><span class="sxs-lookup"><span data-stu-id="78c93-104">Linear algebra is the language of quantum computing.</span></span> <span data-ttu-id="78c93-105">雖然不了解線性代數也可以實作或撰寫量子程式，但線性代數卻廣泛用於描述量子位元狀態、量子運算，以及用於預測量子電腦為了回應一連串指示所會執行的動作。</span><span class="sxs-lookup"><span data-stu-id="78c93-105">Although you don’t need to know it to implement or write quantum programs, it is widely used to describe qubit states, quantum operations, and to predict what a quantum computer will do in response to a sequence of instructions.</span></span>

<span data-ttu-id="78c93-106">熟悉[量子物理的基本概念](xref:microsoft.quantum.overview.understanding)可以協助您了解量子運算，同樣地，了解一些基本的線性代數也可以協助您了解量子演算法的運作方式。</span><span class="sxs-lookup"><span data-stu-id="78c93-106">Just like being familiar with the [basic concepts of quantum physics](xref:microsoft.quantum.overview.understanding) can help you understand quantum computing, knowing some basic linear algebra can help you understand how quantum algorithms work.</span></span> <span data-ttu-id="78c93-107">至少請熟悉**向量**和**矩陣乘法**。</span><span class="sxs-lookup"><span data-stu-id="78c93-107">At the least, you’ll want to be familiar with **vectors** and **matrix multiplication**.</span></span> <span data-ttu-id="78c93-108">如果您需要複習這些代數概念知識，以下是一些涵蓋基本知識的教學課程：</span><span class="sxs-lookup"><span data-stu-id="78c93-108">If you need to refresh your knowledge of these algebra concepts, here are some tutorials that cover the basics:</span></span>

- [<span data-ttu-id="78c93-109">關於線性代數的 Jupyter 筆記本教學課程</span><span class="sxs-lookup"><span data-stu-id="78c93-109">Jupyter notebook tutorial on linear algebra</span></span>](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [<span data-ttu-id="78c93-110">關於複數運算的 Jupyter 筆記本教學課程</span><span class="sxs-lookup"><span data-stu-id="78c93-110">Jupyter notebook tutorial on complex arithmetic</span></span>](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [<span data-ttu-id="78c93-111">量子運算的線性代數</span><span class="sxs-lookup"><span data-stu-id="78c93-111">Linear Algebra for Quantum Computation</span></span>](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [<span data-ttu-id="78c93-112">線性代數的基本概念</span><span class="sxs-lookup"><span data-stu-id="78c93-112">Fundamentals of Linear Algebra</span></span>](https://www.math.ubc.ca/~carrell/NB.pdf)
- [<span data-ttu-id="78c93-113">量子運算入門</span><span class="sxs-lookup"><span data-stu-id="78c93-113">Quantum Computation Primer</span></span>](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a><span data-ttu-id="78c93-114">量子運算中的向量和矩陣</span><span class="sxs-lookup"><span data-stu-id="78c93-114">Vectors and matrices in quantum computing</span></span>

<span data-ttu-id="78c93-115">在[了解量子運算](xref:microsoft.quantum.overview.understanding)的主題中，您曾看到量子位元的狀態可以是 1 或 0 或疊加或兩者。</span><span class="sxs-lookup"><span data-stu-id="78c93-115">In the topic [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), you saw that a qubit can be in a state of 1 or 0 or a superposition or both.</span></span> <span data-ttu-id="78c93-116">使用線性代數時，量子位元的狀態可以用向量加以描述，並以單行**矩陣** $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 來呈現。</span><span class="sxs-lookup"><span data-stu-id="78c93-116">Using linear algebra, the state of a qubit is described as a vector and is represented by a single column **matrix** $\begin{bmatrix} a \\\\  b \end{bmatrix}$.</span></span> <span data-ttu-id="78c93-117">這也稱為**量子狀態向量**，而且必須符合 $|a|^2 + |b|^2 = 1$ 的要求。</span><span class="sxs-lookup"><span data-stu-id="78c93-117">It is also known as a **quantum state vector** and must meet the requirement that $|a|^2 + |b|^2 = 1$.</span></span>  

<span data-ttu-id="78c93-118">矩陣的元素代表量子位元塌縮向某一方的概率，其中 $|a|^2$ 是塌縮為 0 的概率，而 $|b|^2$ 則是塌縮為 1 的概率。</span><span class="sxs-lookup"><span data-stu-id="78c93-118">The elements of the matrix represent the probability of the qubit collapsing one way or the other, with $|a|^2$ being the probability of collapsing to zero, and $|b|^2$ being the probability of collapsing to one.</span></span> <span data-ttu-id="78c93-119">下列矩陣全都代表有效的量子狀態向量：</span><span class="sxs-lookup"><span data-stu-id="78c93-119">The following matrices all represent valid quantum state vectors:</span></span>

<span data-ttu-id="78c93-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}、\begin{bmatrix} 0 \\\\  1 \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}、\text{ 和 }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="78c93-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span></span>

<span data-ttu-id="78c93-121">在[量子電腦和量子模擬器](xref:microsoft.quantum.overview.simulators)中，您也曾看到量子運算可用來修改量子位元的狀態。</span><span class="sxs-lookup"><span data-stu-id="78c93-121">In [Quantum computers and quantum simulators](xref:microsoft.quantum.overview.simulators) you also saw that quantum operations are used to modify the state of a qubit.</span></span>  <span data-ttu-id="78c93-122">量子運算也可以透過矩陣來表示。</span><span class="sxs-lookup"><span data-stu-id="78c93-122">Quantum operations can also be represented by a matrix.</span></span> <span data-ttu-id="78c93-123">對量子位元套用了量子運算時，其各自的代表矩陣會相乘，產生的答案則代表量子位元在運算後的新狀態。</span><span class="sxs-lookup"><span data-stu-id="78c93-123">When a quantum operation is applied to a qubit, the two matrices that represent them are multiplied and the resulting answer represents the new state of the qubit after the operation.</span></span>  

<span data-ttu-id="78c93-124">以下是以矩陣乘法所呈現的兩個常見量子運算。</span><span class="sxs-lookup"><span data-stu-id="78c93-124">Here are two common quantum operations represented with matrix multiplication.</span></span>


<span data-ttu-id="78c93-125">[`X` 運算](xref:microsoft.quantum.intrinsic.x)會以 Pauli 矩陣 $X$ 來表示，</span><span class="sxs-lookup"><span data-stu-id="78c93-125">The [`X` operation](xref:microsoft.quantum.intrinsic.x) is represented by the Pauli matrix $X$,</span></span>

<span data-ttu-id="78c93-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}，$$</span><span class="sxs-lookup"><span data-stu-id="78c93-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$</span></span>
    
<span data-ttu-id="78c93-127">並可用來將量子位元的狀態從 0 翻轉為 1 (反之亦然)，例如</span><span class="sxs-lookup"><span data-stu-id="78c93-127">and is used to flip the state of a qubit from 0 to 1 (or vice-versa), for example</span></span>

<span data-ttu-id="78c93-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}。$$</span><span class="sxs-lookup"><span data-stu-id="78c93-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="78c93-129">['H' 運算](xref:microsoft.quantum.intrinsic.h)會以 Hadamard 變換 $H$ 來表示，</span><span class="sxs-lookup"><span data-stu-id="78c93-129">The ['H' operation](xref:microsoft.quantum.intrinsic.h) is represented by the Hadamard transformation $H$,</span></span>

<span data-ttu-id="78c93-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}，$$</span><span class="sxs-lookup"><span data-stu-id="78c93-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$</span></span>

 <span data-ttu-id="78c93-131">並且會將量子位元進入疊加態，使其有均等的概率塌縮向任一方，如下所示</span><span class="sxs-lookup"><span data-stu-id="78c93-131">and puts a qubit into a superposition state where it has an even probability of collapsing either way, as shown here</span></span>

<span data-ttu-id="78c93-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}。$$</span><span class="sxs-lookup"><span data-stu-id="78c93-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$</span></span>

<span data-ttu-id="78c93-133">代表量子運算的矩陣有一個要求，那就是其必須是**麼正** (unitary) 矩陣。</span><span class="sxs-lookup"><span data-stu-id="78c93-133">A matrix that represents a quantum operation has one requirement – it must be a **unitary** matrix.</span></span> <span data-ttu-id="78c93-134">如果某個矩陣的**逆**矩陣等於該矩陣的**共軛轉置**矩陣，該矩陣便是麼正矩陣。</span><span class="sxs-lookup"><span data-stu-id="78c93-134">A matrix is unitary if the **inverse** of the matrix is equal to the **conjugate transpose** of the matrix.</span></span>

## <a name="representing-two-qubit-states"></a><span data-ttu-id="78c93-135">代表兩個量子位元狀態</span><span class="sxs-lookup"><span data-stu-id="78c93-135">Representing two-qubit states</span></span>

<span data-ttu-id="78c93-136">在上述範例中，一個量子位元的狀態使用單行矩陣 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 來描述，而對其套用運算的行為則以乘上兩個矩陣來描述。</span><span class="sxs-lookup"><span data-stu-id="78c93-136">In the examples above, the state of one qubit was described using a single column matrix $\begin{bmatrix} a \\\\  b \end{bmatrix}$, and applying an operation to it was described by multiplying the two matrices.</span></span> <span data-ttu-id="78c93-137">不過，量子電腦會使用多個量子位元，因此該如何描述兩個量子位元的結合狀態呢？</span><span class="sxs-lookup"><span data-stu-id="78c93-137">However, quantum computers use more than one qubit, so how do you describe the combined state of two qubits?</span></span> 

<span data-ttu-id="78c93-138">請記住，每個量子位元都是一個向量空間，因此不能直接相乘。</span><span class="sxs-lookup"><span data-stu-id="78c93-138">Remember that each qubit is a vector space, so they can't just be multiplied.</span></span> <span data-ttu-id="78c93-139">相反地，您必須使用**張量積**，這是一種相關運算，會從個別向量空間建立新的向量空間，並以 $\otimes $ 符號表示。</span><span class="sxs-lookup"><span data-stu-id="78c93-139">Instead, you use a **tensor product**, which is a related operation that creates a new vector space from individual vector spaces, and is represented by the $\otimes$ symbol.</span></span> <span data-ttu-id="78c93-140">例如，兩個量子位元狀態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 和 $\begin{bmatrix} c \\\\  d \end{bmatrix}$ 的張量積計算如下</span><span class="sxs-lookup"><span data-stu-id="78c93-140">For example, the tensor product of two qubit states $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$ is calculated</span></span>

<span data-ttu-id="78c93-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="78c93-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.</span></span> $$

<span data-ttu-id="78c93-142">所得結果是一個四維矩陣，每個元素各自代表一個概率。</span><span class="sxs-lookup"><span data-stu-id="78c93-142">The result is a four-dimensional matrix, with each element representing a probability.</span></span> <span data-ttu-id="78c93-143">例如，$ac$ 是塌縮為 0 和 0 的兩個量子位元所具有的概率，$ad$ 則是 0 和 1 的概率，依此類推。</span><span class="sxs-lookup"><span data-stu-id="78c93-143">For example, $ac$ is the probability of the two qubits collapsing to 0 and 0, $ad$ is the probability of 0 and 1, and so on.</span></span> 

<span data-ttu-id="78c93-144">單一量子位元狀態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 必須符合 $|a|^2 + |b|^2 = 1$ 的要求才能表示量子狀態，同樣地，雙量子位元的狀態 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ 也必須符合 $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$ 的要求。</span><span class="sxs-lookup"><span data-stu-id="78c93-144">Just as a single qubit state $\begin{bmatrix} a \\\\  b \end{bmatrix}$ must meet the requirement that $|a|^2 + |b|^2 = 1$ in order to represent a quantum state, a two-qubit state $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ must meet the requirement that $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.</span></span>

## <a name="summary"></a><span data-ttu-id="78c93-145">摘要</span><span class="sxs-lookup"><span data-stu-id="78c93-145">Summary</span></span>

<span data-ttu-id="78c93-146">線性代數是用來描述量子運算和量子物理的標準語言。</span><span class="sxs-lookup"><span data-stu-id="78c93-146">Linear algebra is the standard language for describing quantum computing and quantum physics.</span></span> <span data-ttu-id="78c93-147">雖然 Microsoft Quantum 開發套件隨附的[程式庫](xref:microsoft.quantum.libraries)可協助您不必深入了解基礎的數學運算就能執行進階的量子演算法，但了解基本概念可協助您快速入門，並提供扎實的建立基礎。</span><span class="sxs-lookup"><span data-stu-id="78c93-147">Even though the [libraries](xref:microsoft.quantum.libraries) included with the Microsoft Quantum Development Kit will help you run advanced quantum algorithms without diving into the underlying math, understanding the basics will help you get started quickly and provide a solid foundation to build on.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78c93-148">後續步驟</span><span class="sxs-lookup"><span data-stu-id="78c93-148">Next steps</span></span>

[<span data-ttu-id="78c93-149">安裝 QDK</span><span class="sxs-lookup"><span data-stu-id="78c93-149">Install the QDK</span></span>](xref:microsoft.quantum.install)
