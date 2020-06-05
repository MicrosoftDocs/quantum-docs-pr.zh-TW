---
title: 量子電腦和量子模擬器
description: 了解量子硬體、量子模擬器，以及量子運算的運作方式。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 2f5345504ba31211c97493e78af1563d575881e4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327742"
---
# <a name="quantum-computers-and-quantum-simulators"></a><span data-ttu-id="ccb29-103">量子電腦和量子模擬器</span><span class="sxs-lookup"><span data-stu-id="ccb29-103">Quantum computers and quantum simulators</span></span>

<span data-ttu-id="ccb29-104">量子電腦仍處於發展初期。</span><span class="sxs-lookup"><span data-stu-id="ccb29-104">Quantum computers are still in the infancy of their development.</span></span> <span data-ttu-id="ccb29-105">硬體和維護成本很高，而且大部分系統都位於大學和研究實驗室。</span><span class="sxs-lookup"><span data-stu-id="ccb29-105">The hardware and maintenance are expensive, and most systems are located in universities and research labs.</span></span> <span data-ttu-id="ccb29-106">不過，這項技術正在不斷進步，而且有一些系統已經有限度地開放存取。</span><span class="sxs-lookup"><span data-stu-id="ccb29-106">The technology is advancing, though, and limited public access to some systems is available.</span></span>

<span data-ttu-id="ccb29-107">量子模擬器是可在傳統電腦上執行的軟體程式，並可讓您在會預測量子位元將如何回應不同運算的環境中執行和測試量子程式。</span><span class="sxs-lookup"><span data-stu-id="ccb29-107">Quantum simulators are software programs that run on classical computers and make it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span>

## <a name="quantum-hardware"></a><span data-ttu-id="ccb29-108">量子硬體</span><span class="sxs-lookup"><span data-stu-id="ccb29-108">Quantum hardware</span></span>

<span data-ttu-id="ccb29-109">量子電腦有三個主要部分：裝載量子位元的區域、用來將訊號傳送至量子位元的方法，以及用來執行程式和傳送指示的傳統電腦。</span><span class="sxs-lookup"><span data-stu-id="ccb29-109">A quantum computer has three primary parts: an area that houses the qubits, a method for transferring signals to the qubits, and a classical computer to run a program and send instructions.</span></span>

- <span data-ttu-id="ccb29-110">用於量子位元的量子材料非常脆弱，而且對於環境的干涉異常敏感。</span><span class="sxs-lookup"><span data-stu-id="ccb29-110">The quantum material used for qubits is fragile and highly sensitive to environmental interferences.</span></span> <span data-ttu-id="ccb29-111">對於某些量子位元儲存方法來說，裝載量子位元的單位會保持在比絕對零度略高的溫度，以便其能夠達到最大相干性。</span><span class="sxs-lookup"><span data-stu-id="ccb29-111">For some methods of qubit storage, the unit that houses the qubits is kept at a temperature just above absolute zero to maximize their coherence.</span></span> <span data-ttu-id="ccb29-112">其他類型的量子位元裝載則會使用真空室以便將震動降到最低，並使量子位元保持穩定。</span><span class="sxs-lookup"><span data-stu-id="ccb29-112">Other types of qubit housing use a vacuum chamber to help minimize vibrations and stabilize the qubits.</span></span>  
- <span data-ttu-id="ccb29-113">您可以使用各種不同的方法 (包括微波、鐳射和電壓) 將訊號傳送至量子位元。</span><span class="sxs-lookup"><span data-stu-id="ccb29-113">Signals can be sent to the qubits using a variety of methods including microwaves, laser, and voltage.</span></span>

<span data-ttu-id="ccb29-114">量子電腦面臨許多挑戰，因此難以正常運作。</span><span class="sxs-lookup"><span data-stu-id="ccb29-114">Quantum computers face a multitude of challenges to operate correctly.</span></span> <span data-ttu-id="ccb29-115">量子電腦的錯誤修正是一大問題，而且擴大 (新增更多量子位元) 時將會提高錯誤發生率。</span><span class="sxs-lookup"><span data-stu-id="ccb29-115">Error correction in quantum computers is a significant issue, and scaling up (adding more qubits) increases the error rate.</span></span> <span data-ttu-id="ccb29-116">基於這些限制，桌上型量子電腦想要問世仍是遙遙無期，但具有商業可行性的實驗室型量子電腦會比較早問世。</span><span class="sxs-lookup"><span data-stu-id="ccb29-116">Because of these limitations, a quantum PC for your desktop is far in the future, but a commercially-viable lab-based quantum computer is closer.</span></span>

## <a name="quantum-simulators"></a><span data-ttu-id="ccb29-117">量子模擬器</span><span class="sxs-lookup"><span data-stu-id="ccb29-117">Quantum simulators</span></span>

<span data-ttu-id="ccb29-118">在傳統電腦上執行的量子模擬器可讓您模擬量子演算法在量子系統上的執行情形。</span><span class="sxs-lookup"><span data-stu-id="ccb29-118">Quantum simulators that run on classical computers allow you to simulate the execution of quantum algorithms on a quantum system.</span></span>  <span data-ttu-id="ccb29-119">Microsoft Quantum 開發套件 (QDK) 包含全狀態的向量模擬器，以及其他特製化的量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="ccb29-119">Microsoft’s Quantum Development Kit (QDK) includes a full-state vector simulator along with other specialized quantum simulators.</span></span>

## <a name="topological-qubit"></a><span data-ttu-id="ccb29-120">拓撲量子位元</span><span class="sxs-lookup"><span data-stu-id="ccb29-120">Topological qubit</span></span>

<span data-ttu-id="ccb29-121">Microsoft 正在根據拓撲量子位元來開發量子電腦。</span><span class="sxs-lookup"><span data-stu-id="ccb29-121">Microsoft is developing a quantum computer based on topological qubits.</span></span> <span data-ttu-id="ccb29-122">拓撲量子位元較不會受到其環境變化所影響，因此可減少所需的外部糾錯程度。</span><span class="sxs-lookup"><span data-stu-id="ccb29-122">A topological qubit will be less impacted by changes in its environment, therefore reducing the degree of external error correction required.</span></span>

<span data-ttu-id="ccb29-123">拓撲量子位元提高了穩定性和對抗環境雜訊的能力，這表示它們可以更輕鬆地調整規模，並長期保持可靠。</span><span class="sxs-lookup"><span data-stu-id="ccb29-123">Topological qubits feature increased stability and resistance to environmental noise, which means they can more readily scale and remain reliable longer.</span></span>

## <a name="microsoft-and-quantum-hardware-partnerships"></a><span data-ttu-id="ccb29-124">Microsoft 與量子硬體的合作關係</span><span class="sxs-lookup"><span data-stu-id="ccb29-124">Microsoft and quantum hardware partnerships</span></span>

<span data-ttu-id="ccb29-125">Microsoft 與量子硬體製造商 IonQ、Honeywell 和 QCI 合作，以便讓開發人員能夠在未來存取量子電腦。</span><span class="sxs-lookup"><span data-stu-id="ccb29-125">Microsoft is partnering with quantum hardware manufacturers IonQ, Honeywell, and QCI to make quantum computers accessible to developers in the future.</span></span> <span data-ttu-id="ccb29-126">利用 Azure Quantum 平台，開發人員將能夠使用 Microsoft Quantum 開發套件 (QDK) 和 Q# 來撰寫量子程式並從遠端執行。</span><span class="sxs-lookup"><span data-stu-id="ccb29-126">Leveraging the Azure Quantum platform, developers will be able to use Microsoft’s Quantum Development Kit (QDK) and Q# to write quantum programs and run them remotely.</span></span>

## <a name="quantum-computations"></a><span data-ttu-id="ccb29-127">量子運算</span><span class="sxs-lookup"><span data-stu-id="ccb29-127">Quantum computations</span></span>

<span data-ttu-id="ccb29-128">在量子電腦或量子模擬器上執行運算時，會遵循以下基本程序：</span><span class="sxs-lookup"><span data-stu-id="ccb29-128">Performing computations on a quantum computer or quantum simulator follow a basic process:</span></span>

- <span data-ttu-id="ccb29-129">存取量子位元</span><span class="sxs-lookup"><span data-stu-id="ccb29-129">Access the qubits</span></span>
- <span data-ttu-id="ccb29-130">將量子位元初始化為所需狀態</span><span class="sxs-lookup"><span data-stu-id="ccb29-130">Initialize the qubits to the desired state</span></span>
- <span data-ttu-id="ccb29-131">執行運算以轉換量子位元的狀態</span><span class="sxs-lookup"><span data-stu-id="ccb29-131">Perform operations to transform the states of the qubits</span></span>
- <span data-ttu-id="ccb29-132">測量量子位元的新狀態</span><span class="sxs-lookup"><span data-stu-id="ccb29-132">Measure the new states of the qubits</span></span>

<span data-ttu-id="ccb29-133">量子位元的初始化和轉換可使用**量子運算** (有時稱為量子閘) 來完成。</span><span class="sxs-lookup"><span data-stu-id="ccb29-133">Initializing and transforming qubits is done using **quantum operations** (sometimes called quantum gates).</span></span> <span data-ttu-id="ccb29-134">量子運算類似於傳統運算中的邏輯運算，例如 AND、OR、NOT 和 XOR。</span><span class="sxs-lookup"><span data-stu-id="ccb29-134">Quantum operations are similar to logic operations in classical computing, such as AND, OR, NOT, and XOR.</span></span> <span data-ttu-id="ccb29-135">運算可以基本到像是將量子位元的狀態從 1 翻轉為 0 或是糾纏一對量子位元，以便使用一系列的多個運算來影響塌縮至其中一方的疊加量子位元概率。</span><span class="sxs-lookup"><span data-stu-id="ccb29-135">An operation can be as basic as flipping a qubit's state from 1 to 0 or entangling a pair of qubits, to using multiple operations in series to affect the probability of a superposed qubit collapsing one way or the other.</span></span>

> [!NOTE] 
> <span data-ttu-id="ccb29-136">[Q# 程式庫](xref:microsoft.quantum.libraries)提供了內建運算，可定義較低層級量子運算的複雜組合。</span><span class="sxs-lookup"><span data-stu-id="ccb29-136">The [Q# libraries](xref:microsoft.quantum.libraries) provide built-in operations that define complex combinations of lower-level quantum operations.</span></span> <span data-ttu-id="ccb29-137">您可以使用程式庫運算來轉換量子位元，以及建立更複雜的使用者定義運算。</span><span class="sxs-lookup"><span data-stu-id="ccb29-137">You can use the library operations to transform qubits and to create more complex user-defined operations.</span></span>  

<span data-ttu-id="ccb29-138">測量運算結果會告訴我們答案，但對於某些量子演算法來說，卻不一定是正確的答案。</span><span class="sxs-lookup"><span data-stu-id="ccb29-138">Measuring the result of the computation tells us an answer, but for some quantum algorithms, not necessarily the correct answer.</span></span> <span data-ttu-id="ccb29-139">由於某些量子演算法的結果是以量子運算所設定的概率作為基礎，因此這些運算會執行多次以取得概率分佈，並提升結果的精確度。</span><span class="sxs-lookup"><span data-stu-id="ccb29-139">Because the result of some quantum algorithms is based on the probability that was configured by the quantum operations, these computations are run multiple times to get a probability distribution and refine the accuracy of the results.</span></span>  <span data-ttu-id="ccb29-140">運算會傳回正確答案的保證就是所謂的量子驗證，但這在量子運算中是一大挑戰。</span><span class="sxs-lookup"><span data-stu-id="ccb29-140">Assurance that an operation returned a correct answer is known as quantum verification and is a significant challenge in quantum computing.</span></span>

## <a name="summary"></a><span data-ttu-id="ccb29-141">摘要</span><span class="sxs-lookup"><span data-stu-id="ccb29-141">Summary</span></span>

<span data-ttu-id="ccb29-142">量子運算與傳統運算共用了一些相同的概念，但新增了幾個新的轉變。</span><span class="sxs-lookup"><span data-stu-id="ccb29-142">Quantum computing shares some of the same concepts as classical computing but adds a few new twists.</span></span> <span data-ttu-id="ccb29-143">以下是一些重點：</span><span class="sxs-lookup"><span data-stu-id="ccb29-143">Here are some key takeaways:</span></span>

- <span data-ttu-id="ccb29-144">量子硬體成本高昂且很脆弱，因此會使用量子模擬器來撰寫和測試程式。</span><span class="sxs-lookup"><span data-stu-id="ccb29-144">Quantum hardware is expensive and fragile to work with, so quantum simulators are used to write and test programs.</span></span>
- <span data-ttu-id="ccb29-145">傳統電腦和量子電腦都會使用邏輯運算 (或邏輯閘) 來準備運算。</span><span class="sxs-lookup"><span data-stu-id="ccb29-145">Both classical and quantum computers use logic operations (or gates) to prepare computations.</span></span>
- <span data-ttu-id="ccb29-146">量子運算會傳回概率。</span><span class="sxs-lookup"><span data-stu-id="ccb29-146">Quantum computations return probabilities.</span></span>

<span data-ttu-id="ccb29-147">量子硬體和技術的進步正在快速改變這個領域。</span><span class="sxs-lookup"><span data-stu-id="ccb29-147">Advancements in quantum hardware and techniques is rapidly changing the field.</span></span> <span data-ttu-id="ccb29-148">以下只是幾個[目前的發展](https://phys.org/search/?search=quantum+computer&s=0)。</span><span class="sxs-lookup"><span data-stu-id="ccb29-148">Here are just a few of the [current developments](https://phys.org/search/?search=quantum+computer&s=0).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ccb29-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ccb29-149">Next steps</span></span>

[<span data-ttu-id="ccb29-150">Q# 程式設計語言和 QDK 是什麼？</span><span class="sxs-lookup"><span data-stu-id="ccb29-150">What are the Q# programming language and QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)
