---
title: 多個 qubits |Microsoft Docs
description: 多個 qubits
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3e0404cfd67f693ff6b7a8297566e59208fc7ec0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183772"
---
# <a name="multiple-qubits"></a><span data-ttu-id="7e02e-103">多個 Qubits</span><span class="sxs-lookup"><span data-stu-id="7e02e-103">Multiple Qubits</span></span>

<span data-ttu-id="7e02e-104">雖然單一 qubit 閘道具有一些非常直覺的功能，例如能夠在指定時間處於一個以上的狀態，但如果您在量子電腦中只有單一 qubit 的閘道，則會有一個裝置具有可小巫見大巫的計算能力即使是計算機也可以單獨使用傳統超級電腦。</span><span class="sxs-lookup"><span data-stu-id="7e02e-104">While single-qubit gates possess some counter-intuitive features, such as the ability to be in more than one state at a given time, if all we had in a quantum computer were single-qubit gates then we would have a device with computational power that would be dwarfed by even a calculator let alone a classical supercomputer.</span></span>
<span data-ttu-id="7e02e-105">只有當我們增加 qubits 數目時，才會明顯地看到量子運算的真正威力。</span><span class="sxs-lookup"><span data-stu-id="7e02e-105">The true power of quantum computing only becomes evident as we increase the number of qubits.</span></span>
<span data-ttu-id="7e02e-106">這項功能的發生原因是，配量狀態向量的向量空間維度，會隨著 qubits 的數目以指數方式成長。</span><span class="sxs-lookup"><span data-stu-id="7e02e-106">This power arises, in part, because the dimension of the vector space of quantum state vectors grows exponentially with the number of qubits.</span></span>
<span data-ttu-id="7e02e-107">這表示，雖然單一 qubit 可以完整模型化，但是模擬 50 qubit 的量子計算可能會推送現有超級電腦的限制。</span><span class="sxs-lookup"><span data-stu-id="7e02e-107">This means that while a single qubit can be trivially modeled, simulating a fifty-qubit quantum computation would arguably push the limits of existing supercomputers.</span></span>
<span data-ttu-id="7e02e-108">只有一個額外的 qubit 會增加計算的大小，這會使儲存狀態所需的記憶體*加倍*，而且大約是計算時間*加倍*。</span><span class="sxs-lookup"><span data-stu-id="7e02e-108">Increasing the size of the computation by only one additional qubit *doubles* the memory required to store the state and roughly *doubles* the computational time.</span></span>
<span data-ttu-id="7e02e-109">這倍的運算能力很快就是為什麼配量電腦的 qubits 數量相對較少，在某些計算工作中的超級電腦最強大。</span><span class="sxs-lookup"><span data-stu-id="7e02e-109">This rapid doubling of computational power is why a quantum computer with a relatively small number of qubits can far surpass the most powerful supercomputers of today, tomorrow and beyond for some computational tasks.</span></span>

<span data-ttu-id="7e02e-110">為什麼會有量子狀態向量的指數成長？</span><span class="sxs-lookup"><span data-stu-id="7e02e-110">Why do we have exponential growth for quantum state vectors?</span></span>  <span data-ttu-id="7e02e-111">本節的目標是要探討用來建立多 qubit 狀態的規則，而不是單一 qubit 的狀態，以及討論我們需要在閘道集中包含的閘道作業，以構成通用的多 qubit 量子電腦。</span><span class="sxs-lookup"><span data-stu-id="7e02e-111">Our goal in this section is to review the rules used to build multi-qubit states out of single-qubit states as well as discuss the gate operations that we need to include in our gate set to form a universal many-qubit quantum computer.</span></span>
<span data-ttu-id="7e02e-112">這些工具絕對需要用來瞭解問 # 程式碼中常用的閘道集，也可以取得直覺的原因，例如會任何牽連或干擾轉譯配量計算比傳統運算更強大。</span><span class="sxs-lookup"><span data-stu-id="7e02e-112">These tools are absolutely necessary to understand the gate sets that are commonly used in Q# code and also to gain intuition about why quantum effects such as entanglement or interference render quantum computing more powerful than classical computing.</span></span>

## <a name="representing-two-qubits"></a><span data-ttu-id="7e02e-113">代表兩個 Qubits</span><span class="sxs-lookup"><span data-stu-id="7e02e-113">Representing Two Qubits</span></span>
<span data-ttu-id="7e02e-114">一到兩個 qubit 狀態的主要差異在於兩個 qubit 的狀態是四維，而不是二維。</span><span class="sxs-lookup"><span data-stu-id="7e02e-114">The main difference between one- and two-qubit states is that two-qubit states are four dimensional rather than two dimensional.</span></span>
<span data-ttu-id="7e02e-115">這是因為兩個 qubit 狀態的計算基礎是由一 qubit 狀態的張量產品所組成。</span><span class="sxs-lookup"><span data-stu-id="7e02e-115">This is because the computational basis for two-qubit states is formed by the tensor products of one-qubit states.</span></span>  <span data-ttu-id="7e02e-116">例如，我們有 \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}、\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}、\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}、\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-116">For example, we have \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix},\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix},\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.</span></span>
<span data-ttu-id="7e02e-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7e02e-117">\end{align}</span></span>

<span data-ttu-id="7e02e-118">很容易看到，$n $ qubits 的配量狀態通常是以維度 $ 2 ^ n $ 的單位向量表示，並使用此結構。</span><span class="sxs-lookup"><span data-stu-id="7e02e-118">It is easy to see that more generally the quantum state of $n$ qubits is represented by a unit vector of dimension $2^n$ using this construction.</span></span>  <span data-ttu-id="7e02e-119">向量</span><span class="sxs-lookup"><span data-stu-id="7e02e-119">The vector</span></span>

<span data-ttu-id="7e02e-120">$ $ \begin{bmatrix} \ Alpha_{00} \\\\ \ Alpha_{01} \\\\ \ Alpha_{10} \\\\ \ Alpha_{11} \end{bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-120">$$ \begin{bmatrix} \alpha_{00} \\\\  \alpha_{01} \\\\  \alpha_{10} \\\\  \alpha_{11} \end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-121">代表兩個 qubits 的配量狀態（如果 $ | \ Alpha_{00}| ^ 2 + | \ Alpha_{01}| ^ 2 + | \ Alpha_{10}| ^ 2 + | \ Alpha_{11}| ^ 2 = 1 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-121">represents a quantum state on two qubits if $|\alpha_{00}|^2+|\alpha_{01}|^2+|\alpha_{10}|^2+|\alpha_{11}|^2=1$.</span></span> <span data-ttu-id="7e02e-122">就像單一 qubits，多個 qubits 的量子狀態向量會保存描述系統行為所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="7e02e-122">Just as with single qubits, the quantum state vector of multiple qubits holds all the information needed to describe the system's behavior.</span></span>

<span data-ttu-id="7e02e-123">如果我們提供兩個不同的 qubits，一個在 state $ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $，而第二個 qubit 處於 state $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，對應的雙 qubit 狀態為</span><span class="sxs-lookup"><span data-stu-id="7e02e-123">If we are given two separate qubits, one in the state $\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and a second qubit in the state  $\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$, the corresponding two-qubit state is</span></span>

<span data-ttu-id="7e02e-124">$ $ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \Alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \搶鮮版（Beta） \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \Alpha\gamma \\\\ \Alpha\delta \\\\ \Beta\gamma \\\\ \Beta\delta \end{bmatrix}，$ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-124">$$ \begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} =\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$</span></span>

<span data-ttu-id="7e02e-125">其中，$ \otimes $ 的作業稱為向量的張量產品（或 Kronecker 產品）。</span><span class="sxs-lookup"><span data-stu-id="7e02e-125">where the operation $\otimes$ is called the tensor product (or Kronecker product) of vectors.</span></span> <span data-ttu-id="7e02e-126">請注意，雖然我們一定可以讓兩個單一 qubit 狀態的張量產品形成兩個 qubit 的狀態，而不是所有的兩 qubit 配量狀態都可以撰寫為兩個單一張量狀態的 qubit 產品。</span><span class="sxs-lookup"><span data-stu-id="7e02e-126">Note that while we can always take the tensor product of two single-qubit states to form a two-qubit state, not all two-qubit quantum states can be written as the tensor product of two single-qubit states.</span></span>
<span data-ttu-id="7e02e-127">例如，沒有州 $ \psi = \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $ 和 $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，使其張量產品為狀態</span><span class="sxs-lookup"><span data-stu-id="7e02e-127">For example, there are no states $\psi=\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and $\phi=\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$ such that their tensor product is the state</span></span> 

<span data-ttu-id="7e02e-128">$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-128">$$\psi\otimes \phi = \begin{bmatrix} 1/\sqrt{2} \\\\  0 \\\\  0 \\\\  1/\sqrt{2} \end{bmatrix}.$$</span></span> 

<span data-ttu-id="7e02e-129">這種 qubit 狀態無法寫入為單一 qubit 狀態的張量產品，稱為「光子狀態」;這兩個 qubits 稱為[*光子*](https://en.wikipedia.org/wiki/Quantum_entanglement)。</span><span class="sxs-lookup"><span data-stu-id="7e02e-129">Such a two-qubit state, which cannot be written as the tensor product of single-qubit states, is called an "entangled state"; the two qubits are said to be [*entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).</span></span>  <span data-ttu-id="7e02e-130">鬆散說，因為無法將配量狀態視為單一 qubit 狀態的張量產品，所以狀態所保存的資訊不會個別限制為任何 qubits。</span><span class="sxs-lookup"><span data-stu-id="7e02e-130">Loosely speaking, because the quantum state cannot be thought of as a tensor product of single qubit states, the information that the state holds is not confined to either of the qubits individually.</span></span>  <span data-ttu-id="7e02e-131">而是在這兩個狀態之間的相互關聯中，以非本機方式儲存資訊。</span><span class="sxs-lookup"><span data-stu-id="7e02e-131">Rather, the information is stored non-locally in the correlations between the two states.</span></span>  <span data-ttu-id="7e02e-132">這種非位置的資訊是傳統運算上的量子運算的其中一項主要區別功能，對於一些量子通訊協定（包括[量子 teleportation](https://github.com/Microsoft/Quantum/tree/master/Samples/src/Teleportation)和[量子錯誤更正](xref:microsoft.quantum.libraries.error-correction)）而言，這是很重要的。</span><span class="sxs-lookup"><span data-stu-id="7e02e-132">This non-locality of information is one of the major distinguishing features of quantum computing over classical computing and is essential for a number of quantum protocols including [quantum teleportation](https://github.com/Microsoft/Quantum/tree/master/Samples/src/Teleportation) and [quantum error correction](xref:microsoft.quantum.libraries.error-correction).</span></span>

## <a name="measuring-two-qubit-states"></a><span data-ttu-id="7e02e-133">測量兩個 Qubit 的狀態</span><span class="sxs-lookup"><span data-stu-id="7e02e-133">Measuring Two-Qubit States</span></span> ##
<span data-ttu-id="7e02e-134">測量兩個 qubit 的狀態與單一 qubit 測量非常類似。</span><span class="sxs-lookup"><span data-stu-id="7e02e-134">Measuring two-qubit states is very similar to single-qubit measurements.</span></span> <span data-ttu-id="7e02e-135">測量狀態</span><span class="sxs-lookup"><span data-stu-id="7e02e-135">Measuring the state</span></span>

<span data-ttu-id="7e02e-136">$ $ \begin{bmatrix} \ Alpha_{00} \\\\ \ Alpha_{01} \\\\ \ Alpha_{10} \\\\ \ Alpha_{11} \end{bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-136">$$ \begin{bmatrix} \alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11} \end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-137">產生 $0 $，機率為 $ | \ Alpha_{00}| ^ $2，$1 $ 具有機率 $ | \ Alpha_{01}| ^ $2，$10 $，機率為 $ | \ Alpha_{10}| ^ $2，而 $11 $ 具有機率 $ | \ Alpha_{11}| ^ $2。</span><span class="sxs-lookup"><span data-stu-id="7e02e-137">yields $00$ with probability $|\alpha_{00}|^2$, $01$ with probability $|\alpha_{01}|^2$, $10$ with probability $|\alpha_{10}|^2$, and $11$ with probability $|\alpha_{11}|^2$.</span></span> <span data-ttu-id="7e02e-138">變數 $ \ Alpha_{00}，\ Alpha_{01}，\ Alpha_{10}，$ 和 $ \ Alpha_{11}$ 已刻意命名，以讓此連接清楚。</span><span class="sxs-lookup"><span data-stu-id="7e02e-138">The variables $\alpha_{00}, \alpha_{01}, \alpha_{10},$ and $\alpha_{11}$ were deliberately named to make this connection clear.</span></span> <span data-ttu-id="7e02e-139">測量之後，如果結果為 $0 $，則兩個 qubit 系統的配量狀態會折迭，現在是</span><span class="sxs-lookup"><span data-stu-id="7e02e-139">After the measurement, if the outcome is $00$ then the quantum state of the two-qubit system has collapsed and is now</span></span>

<span data-ttu-id="7e02e-140">$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-140">$$ 00 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="7e02e-141">您也可以只測量兩個 qubit 量子狀態的一個 qubit。</span><span class="sxs-lookup"><span data-stu-id="7e02e-141">It is also possible to measure just one qubit of a two-qubit quantum state.</span></span> <span data-ttu-id="7e02e-142">在只測量其中一個 qubits 的情況下，測量的影響會稍微不同，因為整個狀態不會折迭成計算基礎狀態，而只會折迭到一個子系統。</span><span class="sxs-lookup"><span data-stu-id="7e02e-142">In cases where you measure only one of the qubits, the impact of measurement is subtly different because the entire state is not collapsed to a computational basis state, rather it is collapsed to only one sub-system.</span></span>  <span data-ttu-id="7e02e-143">換句話說，在這種情況下，測量只有一個 qubit 只會折迭其中一個子系統，而不是全部折迭。</span><span class="sxs-lookup"><span data-stu-id="7e02e-143">In other words, in such cases measuring only one qubit only collapses one of the subsystems but not all of them.</span></span>  

<span data-ttu-id="7e02e-144">若要瞭解這一點，請考慮測量下列狀態的第一個 qubit，這是透過套用 Hadamard 轉換 $H $ （一開始是設定為 "0" 狀態的兩個 qubits 上所形成）： $ $ H ^ {\otimes 2} \left （\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right） = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &t_10_ \\ 1 &-1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ end {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{cases}\text{outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{案例}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-144">To see this consider measuring the first qubit of the following state, which is formed by applying the Hadamard transform $H$ on two qubits initially set to the "0" state: $$ H^{\otimes 2} \left( \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 & -1 & 1 & -1 \\\\ 1 & 1 & -1 & -1 \\\\ 1 & -1 & -1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0\end{bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \mapsto \begin{cases}\text{outcome }=0 & \frac{1}{\sqrt{2}}\begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome }=1 & \frac{1}{\sqrt{2}}\begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\  \end{cases}.</span></span>
<span data-ttu-id="7e02e-145">$ $ 這兩個結果的發生率為50%。</span><span class="sxs-lookup"><span data-stu-id="7e02e-145">$$ Both outcomes have 50% probability of occurring.</span></span>  <span data-ttu-id="7e02e-146">這兩者的結果為50% 機率的 intuited，是因為第一個 qubit 上的初始配量狀態向量在交換 $0 $1 $ 底下不變。</span><span class="sxs-lookup"><span data-stu-id="7e02e-146">The outcome being 50% probability for both can be intuited from the fact that the initial quantum state vector is invariant under swapping $0$ with $1$ on the first qubit.</span></span>

<span data-ttu-id="7e02e-147">測量第一個或第二個 qubit 的數學規則很簡單。</span><span class="sxs-lookup"><span data-stu-id="7e02e-147">The mathematical rule for measuring the first or second qubit is simple.</span></span>  <span data-ttu-id="7e02e-148">如果我們讓 $e _k $ 是 $k ^ {\rm th} $ 計算基礎向量，並讓 $S $ 是所有 $e $ 的集合，如此一來，問題的 qubit 就會將該值 _k $ 的值設為 $1 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-148">If we let $e_k$ be the $k^{\rm th}$ computational basis vector and let $S$ be the set of all $e_k$ such that the qubit in question takes the value $1$ for that value of $k$.</span></span>  <span data-ttu-id="7e02e-149">例如，如果我們有興趣測量第一個 qubit，則 $S $ 會包含 $e _2 \ HTTP-equiv $10 和 $e _3 \ HTTP-equiv $11。</span><span class="sxs-lookup"><span data-stu-id="7e02e-149">For example, if we are interested in measuring the first qubit then $S$ would consist of $e_2\equiv 10$ and $e_3\equiv 11$.</span></span>  <span data-ttu-id="7e02e-150">同樣地，如果我們對第二個 qubit 有興趣 $S $ 會包含 $e _1 \ HTTP-equiv $1 和 $e _3 \equiv $11。</span><span class="sxs-lookup"><span data-stu-id="7e02e-150">Similarly, if we are interested in the second qubit $S$ would consist of $e_1\equiv 01$ and $e_3 \equiv 11$.</span></span>  <span data-ttu-id="7e02e-151">然後，測量所選 qubit 為 $1 $ 的機率是針對狀態向量 $ \psi $</span><span class="sxs-lookup"><span data-stu-id="7e02e-151">Then the probability of measuring the chosen qubit to be $1$ is for state vector $\psi$</span></span>

<span data-ttu-id="7e02e-152">$ $ P （\text{outcome} = 1） = \ sum_ {e_k 集合中的 \text{} S} \psi ^ \dagger e_k e_k ^ \dagger \psi。</span><span class="sxs-lookup"><span data-stu-id="7e02e-152">$$ P(\text{outcome}=1)= \sum_{e_k \text{ in the set } S}\psi^\dagger e_k e_k^\dagger \psi.</span></span>
$$

<span data-ttu-id="7e02e-153">由於每個 qubit 量測只能產生 $0 $ 或 $1 $，測量 $0 $ 的機率只是 $1-P （\text{outcome} = 1） $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-153">Since each qubit measurement can only yield $0$ or $1$, the probability of measuring $0$ is simply $1-P(\text{outcome}=1)$.</span></span>  <span data-ttu-id="7e02e-154">這就是為什麼我們只會針對測量 $1 $ 的機率明確提供公式。</span><span class="sxs-lookup"><span data-stu-id="7e02e-154">This is why we only explicitly give a formula for the probability of measuring $1$.</span></span>

<span data-ttu-id="7e02e-155">這類測量具有狀態的動作可以數學方式表示為</span><span class="sxs-lookup"><span data-stu-id="7e02e-155">The action that such a measurement has on the state can be expressed mathematically as</span></span>

<span data-ttu-id="7e02e-156">$ $ \psi \mapsto \frac{\ sum_ {e_k \text{在 set} S} e_k e_k ^ \dagger \psi}{\sqrt{P （\text{outcome} = 1）}}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-156">$$ \psi \mapsto \frac{\sum_{e_k \text{ in the set } S} e_k e_k^\dagger \psi}{\sqrt{P(\text{outcome}=1)}}.</span></span>
$$

<span data-ttu-id="7e02e-157">謹慎的讀者可能會擔心測量的機率為零時，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="7e02e-157">The cautious reader may worry about what happens when the probability of the measurement is zero.</span></span>  <span data-ttu-id="7e02e-158">雖然在此情況下，結果狀態是未定義的，但我們不需要擔心這類 eventualities，因為機率為零！</span><span class="sxs-lookup"><span data-stu-id="7e02e-158">While the resultant state is technically undefined in this case, we never need to worry about such eventualities because the probability is zero!</span></span>


<span data-ttu-id="7e02e-159">如果我們將 $ \psi $ 視為上述的統一狀態向量，並有興趣測量第一個 qubit，</span><span class="sxs-lookup"><span data-stu-id="7e02e-159">If we take $\psi$ to be the uniform state vector given above and are interested in measuring the first qubit then</span></span> 

<span data-ttu-id="7e02e-160">$ $ P （第一個 qubit 的 \text{measurement} = 1） = （\psi ^ \dagger e_2）（e_2 ^ \dagger \psi） + （\psi ^ \dagger e_3）（e_3 ^ \dagger \psi） = | e_2 ^ \dagger \psi | ^ 2。</span><span class="sxs-lookup"><span data-stu-id="7e02e-160">$$ P(\text{measurement of first qubit}=1) = (\psi^\dagger e_2)(e_2^\dagger \psi)+(\psi^\dagger e_3)(e_3^\dagger \psi)=|e_2^\dagger \psi|^2+|e_3^\dagger \psi|^2.</span></span>
$$

<span data-ttu-id="7e02e-161">請注意，這只是測量結果 $10 $ 和 $11 $ 所預期的兩個機率的總和，全都是要測量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="7e02e-161">Note that this is just the sum of the two probabilities that would be expected for measuring the results $10$ and $11$ were all the qubits to be measured.</span></span>
<span data-ttu-id="7e02e-162">在我們的範例中，這會評估為</span><span class="sxs-lookup"><span data-stu-id="7e02e-162">For our example, this evaluates to</span></span>

<span data-ttu-id="7e02e-163">$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ 結束 {bmatrix} \ begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \開始 {bmatrix} 0 & 0 & 0 & 1 \ end {bmatrix} \ begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-163">$$ \frac{1}{4}\left|\begin{bmatrix}0&0&1&0\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2+\frac{1}{4}\left|\begin{bmatrix}0&0&0&1\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2=\frac{1}{2}.</span></span>
$$

<span data-ttu-id="7e02e-164">這完全符合我們的直覺告訴我們機率的可能性。</span><span class="sxs-lookup"><span data-stu-id="7e02e-164">which perfectly matches what our intuition tells us the probability should be.</span></span>  <span data-ttu-id="7e02e-165">同樣地，狀態可以寫成</span><span class="sxs-lookup"><span data-stu-id="7e02e-165">Similarly, the state can be written as</span></span>

<span data-ttu-id="7e02e-166">$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-166">$$ \frac{\frac{e_2}{2}+\frac{e_3}{2}}{\sqrt{\frac{1}{2}}}=\frac{1}{\sqrt{2}}\begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1\end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-167">再次遵循我們的直覺。</span><span class="sxs-lookup"><span data-stu-id="7e02e-167">again in accordance with our intuition.</span></span>

## <a name="two-qubit-operations"></a><span data-ttu-id="7e02e-168">兩個 Qubit 的作業</span><span class="sxs-lookup"><span data-stu-id="7e02e-168">Two-Qubit Operations</span></span>
<span data-ttu-id="7e02e-169">就像在單一 qubit 的情況下，任何單一轉換都是 qubits 上的有效操作。</span><span class="sxs-lookup"><span data-stu-id="7e02e-169">As in the single-qubit case, any unitary transformation is a valid operation on qubits.</span></span> <span data-ttu-id="7e02e-170">一般來說，在 $n $ qubits 上的單一轉換是一個大小為 $ 2 ^ n \times 2 ^ n $ 的 $U 矩陣（因此它會作用於大小為 $ 2 ^ n $ 的向量），因此 $U ^{-1} = U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-170">In general, a unitary transformation on $n$ qubits is a matrix $U$ of size $2^n \times 2^n$ (so that it acts on vectors of size $2^n$), such that $U^{-1} = U^\dagger$.</span></span> <span data-ttu-id="7e02e-171">例如，CNOT-CONTAINS （受控制-NOT）閘道是常用的兩個 qubit 閘道，由下列單一矩陣表示：</span><span class="sxs-lookup"><span data-stu-id="7e02e-171">For example, the CNOT (controlled-NOT) gate is a commonly used two-qubit gate and is represented by the following unitary matrix:</span></span>

<span data-ttu-id="7e02e-172">$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-172">$$ \operatorname{CNOT} = \begin{bmatrix} 1\ 0\ 0\ 0  \\\\  0\ 1\ 0\ 0 \\\\  0\ 0\ 0\ 1 \\\\  0\ 0\ 1\ 0 \end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-173">我們也可以在兩個 qubits 上套用單一 qubit 閘道來形成兩個 qubit 的閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-173">We can also form two-qubit gates by applying single-qubit gates on both qubits.</span></span> <span data-ttu-id="7e02e-174">例如，如果我們套用閘道</span><span class="sxs-lookup"><span data-stu-id="7e02e-174">For example, if we apply the gates</span></span> 

<span data-ttu-id="7e02e-175">$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-175">$$ \begin{bmatrix} a\ b\\\\ c\ d \end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-176">與</span><span class="sxs-lookup"><span data-stu-id="7e02e-176">and</span></span>

<span data-ttu-id="7e02e-177">$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $</span><span class="sxs-lookup"><span data-stu-id="7e02e-177">$$\begin{bmatrix} e\ f\\\\ g\ h \end{bmatrix} $$</span></span>

<span data-ttu-id="7e02e-178">對於第一個和第二個 qubits，這相當於套用張量\\產品所指定的兩個 qubit，\\ c-d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin {bmatrix} ae \ qubit \ bf \\\\ ag \ 張量 \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}. $ $，因此我們可以藉由採用一些已知單一 qubit 閘道的產品來形成兩個的閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-178">to the first and second qubits, respectively, this is equivalent to applying the two-qubit unitary given by their tensor product: $$\begin{bmatrix} a\ b\\\\ c\ d \end{bmatrix} \otimes \begin{bmatrix} e\ f\\\\ g\ h \end{bmatrix}= \begin{bmatrix} ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.$$ Thus we can form two-qubit gates by taking the tensor product of some known single-qubit gates.</span></span> <span data-ttu-id="7e02e-179">兩個 qubit 閘道的一些範例包括 $H \otimes H $、$X \otimes \boldone $ 和 $X \otimes Z $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-179">Some examples of two-qubit gates include $H \otimes H$, $X \otimes \boldone$, and $X \otimes Z$.</span></span>

<span data-ttu-id="7e02e-180">請注意，雖然任何兩個單一 qubit 閘道都是藉由接受張量產品來定義雙 qubit 閘道，相反的情況也不是如此。</span><span class="sxs-lookup"><span data-stu-id="7e02e-180">Note that while any two single-qubit gates define a two-qubit gate by taking their tensor product, the converse is not true.</span></span> <span data-ttu-id="7e02e-181">並非所有的兩個 qubit 閘道都可以撰寫成單一 qubit 閘道的張量產品。</span><span class="sxs-lookup"><span data-stu-id="7e02e-181">Not all two-qubit gates can be written as the tensor product of single-qubit gates.</span></span>  <span data-ttu-id="7e02e-182">這種閘道稱為*entangling*閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-182">Such a gate is called an *entangling* gate.</span></span> <span data-ttu-id="7e02e-183">Entangling 閘道的其中一個範例是 CNOT-CONTAINS 閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-183">One example of an entangling gate is the CNOT gate.</span></span>

<span data-ttu-id="7e02e-184">受控制-not 閘道後方的直覺可以一般化至任意閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-184">The intuition behind a controlled-not gate can be generalized to arbitrary gates.</span></span>  <span data-ttu-id="7e02e-185">受控制的閘道通常是做為身分識別的閘道（即沒有動作），除非特定的 qubit 是 $1 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-185">A controlled gate in general is a gate that acts as identity (ie it has no action) unless a specific qubit is $1$.</span></span>  <span data-ttu-id="7e02e-186">我們在標記為 $x $ 的 qubit 上，以 $ \Lambda\_x （U） $ 表示受控制的單一控制項（在此案例中為）。</span><span class="sxs-lookup"><span data-stu-id="7e02e-186">We denote a controlled unitary, controlled in this case on the qubit labeled $x$, with a $\Lambda\_x(U)$.</span></span>  <span data-ttu-id="7e02e-187">作為範例 $ \ Lambda_0 （U） e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ 和 $ \Lambda\_0 （U） e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $，其中 $e\_$0 和 $e\_$1 是對應至值 $0 $ 和 $1 $ 之單一 qubit 的計算基礎向量。</span><span class="sxs-lookup"><span data-stu-id="7e02e-187">As an example $\Lambda_0(U) e\_{1}\otimes {\psi}=e\_{1}\otimes U{\psi}$ and $\Lambda\_0(U) e\_{0}\otimes {\psi}=e\_{0}\otimes{\psi}$, where $e\_0$ and $e\_1$ are the computational basis vectors for a single qubit corresponding to the values $0$ and $1$.</span></span>  <span data-ttu-id="7e02e-188">例如，請考慮下列受控制的 $Z $ 閘道，然後我們可以將其表示為 $ $ \Lambda\_0 （Z） = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = （\boldone\otimes H） \operatorname{CNOT} （\boldone\otimes H）。</span><span class="sxs-lookup"><span data-stu-id="7e02e-188">For example, consider the following controlled-$Z$ gate then we can express this as $$ \Lambda\_0(Z)= \begin{bmatrix}1&0&0&0\\\\0&1&0&0\\\\0&0&1&0\\\\0&0&0&-1 \end{bmatrix}=(\boldone\otimes H)\operatorname{CNOT}(\boldone\otimes H).</span></span>
$$

<span data-ttu-id="7e02e-189">以有效率的方式建立受控制的 unitaries 是一項重大挑戰。</span><span class="sxs-lookup"><span data-stu-id="7e02e-189">Building controlled unitaries in an efficient manner is a major challenge.</span></span>  <span data-ttu-id="7e02e-190">執行此作業最簡單的方式，就是建立一個受控制版本之基本閘道的資料庫，並將原始單一作業中的每個基本閘道取代為其控制的對應。</span><span class="sxs-lookup"><span data-stu-id="7e02e-190">The simplest way to implement this requires forming a database of controlled versions of fundamental gates and replacing every fundamental gate in the original unitary operation with its controlled counterpart.</span></span>  <span data-ttu-id="7e02e-191">這通常很浪費，而且聰明的深入解析通常可用來以控制的版本來取代幾個閘道，以達到相同的影響。</span><span class="sxs-lookup"><span data-stu-id="7e02e-191">This is often quite wasteful and clever insight often can be used to just replace a few gates with controlled versions to achieve the same impact.</span></span>  <span data-ttu-id="7e02e-192">基於這個理由，我們在架構中提供了一種功能，可以執行控制或允許使用者定義受控制版本的單一（如果已知優化的手動調整版本）。</span><span class="sxs-lookup"><span data-stu-id="7e02e-192">For this reason, we provide in our framework the ability to perform either the naive method of controlling or allow the user to define a controlled version of the unitary if an optimized hand-tuned version is known.</span></span>

<span data-ttu-id="7e02e-193">閘道也可以使用傳統資訊來控制。</span><span class="sxs-lookup"><span data-stu-id="7e02e-193">Gates can also be controlled using classical information.</span></span>  <span data-ttu-id="7e02e-194">例如，傳統方式控制的 not 閘道只是一般的 not 閘道，但只有在傳統位是 $1 $ 而不是配量位時，才會套用。</span><span class="sxs-lookup"><span data-stu-id="7e02e-194">A classically controlled not-gate, for example, is just an ordinary not-gate but it is only applied if a classical bit is $1$ as opposed to a quantum bit.</span></span>  <span data-ttu-id="7e02e-195">就這一點而言，傳統方式控制的閘道可以視為量副程式代碼中的 if 語句，其中閘道只會在程式碼的一個分支中套用。</span><span class="sxs-lookup"><span data-stu-id="7e02e-195">In this sense, a classically controlled gate can be thought of as an if statement in the quantum code wherein the gate is applied only in one branch of the code.</span></span>


<span data-ttu-id="7e02e-196">如同在單一 qubit 的情況中，如果有任何 $ 4 \ 乘以 $4 單一矩陣，則此集合中的閘道的產品可能會將其近似為任意精確度，這兩個 qubit 閘道集會設定為通用。</span><span class="sxs-lookup"><span data-stu-id="7e02e-196">As in the single-qubit case, a two-qubit gate set is universal if any $4\times 4$ unitary matrix can be approximated by a product of gates from this set to arbitrary precision.</span></span>
<span data-ttu-id="7e02e-197">通用閘道集的其中一個範例是 Hadamard 閘道、T 閘道和 CNOT-CONTAINS 閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-197">One example of a universal gate set is the Hadamard gate, the T gate, and the CNOT gate.</span></span> <span data-ttu-id="7e02e-198">藉由取得這些閘道的產品，我們就可以在兩個 qubits 上大致估計任何單一矩陣。</span><span class="sxs-lookup"><span data-stu-id="7e02e-198">By taking products of these gates, we can approximate any unitary matrix on two qubits.</span></span>

## <a name="many-qubit-systems"></a><span data-ttu-id="7e02e-199">多 Qubit 系統</span><span class="sxs-lookup"><span data-stu-id="7e02e-199">Many-Qubit Systems</span></span>
<span data-ttu-id="7e02e-200">我們遵循兩個 qubit 案例中所探索到的相同模式，從較小的系統建立多 qubit 的配量狀態。</span><span class="sxs-lookup"><span data-stu-id="7e02e-200">We follow exactly the same patterns explored in the two-qubit case to build many-qubit quantum states from smaller systems.</span></span>  <span data-ttu-id="7e02e-201">這種狀態是藉由形成較小狀態的張量產品所建立。</span><span class="sxs-lookup"><span data-stu-id="7e02e-201">Such states are built by forming tensor products of smaller states.</span></span>  <span data-ttu-id="7e02e-202">例如，請考慮在量子電腦中編碼位字串 $1011001 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-202">For example, consider encoding the bit string $1011001$ in a quantum computer.</span></span>  <span data-ttu-id="7e02e-203">我們可以將此編碼為</span><span class="sxs-lookup"><span data-stu-id="7e02e-203">We can encode this as</span></span>

<span data-ttu-id="7e02e-204">$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="7e02e-204">$$ 1011001 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="7e02e-205">量子閘道的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="7e02e-205">Quantum gates work in exactly the same way.</span></span>  <span data-ttu-id="7e02e-206">例如，如果我們想要將 $X $ 閘道套用至第一個 qubit，然後在第二個和第三個 qubits 之間執行 CNOT-CONTAINS，我們可以將此轉換表示為</span><span class="sxs-lookup"><span data-stu-id="7e02e-206">For example, if we wish to apply the $X$ gate to the first qubit and then perform a CNOT between the second and third qubits we may express this transformation as</span></span>

<span data-ttu-id="7e02e-207">\begin{align} & （X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone） \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001。</span><span class="sxs-lookup"><span data-stu-id="7e02e-207">\begin{align} &(X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\\\\ &\qquad\qquad\equiv 0011001.</span></span>
<span data-ttu-id="7e02e-208">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7e02e-208">\end{align}</span></span>

<span data-ttu-id="7e02e-209">在許多 qubit 系統中，通常需要配置和取消配置 qubits，做為量子電腦的暫存記憶體。</span><span class="sxs-lookup"><span data-stu-id="7e02e-209">In many qubit systems, there is often a need to allocate and de-allocate qubits that serve as temporary memory for the quantum computer.</span></span>  <span data-ttu-id="7e02e-210">這種 qubit 稱為 ancilla。</span><span class="sxs-lookup"><span data-stu-id="7e02e-210">Such a qubit is called an ancilla.</span></span>  <span data-ttu-id="7e02e-211">根據預設，我們假設 qubit 狀態已初始化為在配置時 $e _0 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-211">By default we assume the qubit state is initialized to $e_0$ upon allocation.</span></span>  <span data-ttu-id="7e02e-212">我們會進一步假設在解除配置之前，會再次傳回 $e _0 $。</span><span class="sxs-lookup"><span data-stu-id="7e02e-212">We further assume that it is returned again to $e_0$ before de-allocation.</span></span>  <span data-ttu-id="7e02e-213">這項假設很重要，因為如果 ancilla qubit 在解除配置時，與另一個 qubit 暫存器光子，則取消配置的程式將會損毀 ancilla。</span><span class="sxs-lookup"><span data-stu-id="7e02e-213">This assumption is important because if an ancilla qubit becomes entangled with another qubit register when it becomes de-allocated then the process of de-allocation will damage the ancilla.</span></span>  <span data-ttu-id="7e02e-214">基於這個理由，我們一律假設這類 qubits 會在發行之前還原成其初始狀態。</span><span class="sxs-lookup"><span data-stu-id="7e02e-214">For this reason, we always assume that such qubits are reverted to their initial state before being released.</span></span>

<span data-ttu-id="7e02e-215">最後，雖然需要將新的閘道新增至閘道，以達到兩個 qubit 量子電腦的通用量子運算，但在多 qubit 的情況下，不需要引進新的閘道。</span><span class="sxs-lookup"><span data-stu-id="7e02e-215">Finally, although new gates needed to be added to our gate set to achieve universal quantum computing for two qubit quantum computers, no new gates need to be introduced in the multi-qubit case.</span></span>  <span data-ttu-id="7e02e-216">閘道 $H $、$T $ 和 CNOT-CONTAINS 會形成在許多 qubits 上設定的通用閘道，因為任何一般的單一轉換都可以分成一系列的兩個 qubit 旋轉。</span><span class="sxs-lookup"><span data-stu-id="7e02e-216">The gates $H$, $T$ and CNOT form a universal gate set on many qubits because any general unitary transformation can be broken into a series of two qubit rotations.</span></span>  <span data-ttu-id="7e02e-217">然後，我們可以利用針對兩個 qubit 案例所開發的理論，並在有許多 qubits 時再次使用。</span><span class="sxs-lookup"><span data-stu-id="7e02e-217">We then can leverage the theory developed for the two-qubit case and use it again here when we have many qubits.</span></span>

<span data-ttu-id="7e02e-218">雖然我們目前使用的線性代數標記法可以用來描述多 qubit 的狀態，但是因為我們增加了狀態的大小，所以變得越來越繁瑣。</span><span class="sxs-lookup"><span data-stu-id="7e02e-218">While the linear algebraic notation that we have been using thus far can certainly be used to describe multi-qubit states, it becomes increasingly cumbersome as we increase the size of the states.</span></span>  <span data-ttu-id="7e02e-219">例如，長度為7位字串的產生的資料行向量為 $128 $ 維，這會使用先前所述的標記法來表示它，這會是非常麻煩的。</span><span class="sxs-lookup"><span data-stu-id="7e02e-219">The resulting column-vector for a length 7 bit string, for example, is $128$ dimensional, which makes expressing it using the notation described previously very cumbersome.</span></span>  <span data-ttu-id="7e02e-220">基於這個理由，我們接下來會在配量運算中呈現常見的標記法，讓我們能夠簡明扼要地描述這些高維度的向量。</span><span class="sxs-lookup"><span data-stu-id="7e02e-220">For this reason, we next present a common notation in quantum computing that allows us to concisely describe these high-dimensional vectors.</span></span>