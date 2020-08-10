---
title: 量子模擬器和 Q# 程式
description: 說明可做為 Q# 程式目標機器的量子模擬器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868299"
---
# <a name="quantum-simulators"></a><span data-ttu-id="3dcac-103">量子模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-103">Quantum simulators</span></span>

<span data-ttu-id="3dcac-104">量子模擬器是可在傳統電腦上執行的軟體程式，能做為 Q# 程式的「目標機器」，可讓您在會預測量子位元將如何回應不同運算的環境中執行和測試量子程式。</span><span class="sxs-lookup"><span data-stu-id="3dcac-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="3dcac-105">本文說明 Quantum 開發套件 (QDK) 中包含哪些量子模擬器，以及將 Q# 程式傳遞至量子模擬器的不同方式，例如透過命令列或使用以傳統語言撰寫的驅動程式程式碼。</span><span class="sxs-lookup"><span data-stu-id="3dcac-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="3dcac-106">Quantum 開發套件 (QDK) 量子模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="3dcac-107">量子模擬器負責為演算法提供量子基元的實作。</span><span class="sxs-lookup"><span data-stu-id="3dcac-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="3dcac-108">這包括基元操作 (例如 `H`、`CNOT`、`Measure`) 以及量子位元的管理和追蹤。</span><span class="sxs-lookup"><span data-stu-id="3dcac-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="3dcac-109">QDK 包含不同的量子模擬器類別，代表相同量子演算法的不同執行模型。</span><span class="sxs-lookup"><span data-stu-id="3dcac-109">The QDK includes different classes of quantum simulators representing different execution models for the same quantum algorithm.</span></span> 


<span data-ttu-id="3dcac-110">每種量子模擬器都可以針對這些基元提供不同的實作。</span><span class="sxs-lookup"><span data-stu-id="3dcac-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="3dcac-111">例如，[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)會藉由完全模擬[量子狀態向量](xref:microsoft.quantum.glossary#quantum-state)來執行量子演算法，而[量子電腦追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)根本不會考慮實際的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="3dcac-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="3dcac-112">相反地，該模擬器會追蹤該演算法的量子閘、量子位元和其他資源使用狀況。</span><span class="sxs-lookup"><span data-stu-id="3dcac-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="3dcac-113">量子機器類別</span><span class="sxs-lookup"><span data-stu-id="3dcac-113">Quantum machine classes</span></span>

<span data-ttu-id="3dcac-114">在未來，QDK 將定義其他量子機器類別，以支援其他類型的模擬，以及支援在量子硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="3dcac-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support execution on quantum hardware.</span></span> <span data-ttu-id="3dcac-115">讓演算法可以在改變基礎機器實作的情況下保持不變，您就可以輕鬆地在模擬中測試演算法並進行偵錯，然後再於真正的硬體上執行，因為您知道演算法並未改變。</span><span class="sxs-lookup"><span data-stu-id="3dcac-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="3dcac-116">QDK 包含數個量子機器類別，全都定義在 `Microsoft.Quantum.Simulation.Simulators` 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="3dcac-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="3dcac-117">模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-117">Simulator</span></span> |<span data-ttu-id="3dcac-118">類別</span><span class="sxs-lookup"><span data-stu-id="3dcac-118">Class</span></span>|<span data-ttu-id="3dcac-119">描述</span><span class="sxs-lookup"><span data-stu-id="3dcac-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="3dcac-120">完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="3dcac-121">執行和偵錯量子演算法，而且限制為大約 30 個量子位元。</span><span class="sxs-lookup"><span data-stu-id="3dcac-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="3dcac-122">簡單資源估算器</span><span class="sxs-lookup"><span data-stu-id="3dcac-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="3dcac-123">對執行量子演算法所需的資源執行最高層級的分析，可支援數千個量子位元。</span><span class="sxs-lookup"><span data-stu-id="3dcac-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="3dcac-124">追蹤型資源估算器</span><span class="sxs-lookup"><span data-stu-id="3dcac-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="3dcac-125">針對演算法的整個呼叫圖執行資源耗用量的進階分析，可支援數千個量子位元。</span><span class="sxs-lookup"><span data-stu-id="3dcac-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="3dcac-126">Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="3dcac-127">模擬的量子演算法僅限於 `X`、`CNOT`、多重控制 `X` 量子作業，可支援百萬個量子位元。</span><span class="sxs-lookup"><span data-stu-id="3dcac-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="3dcac-128">叫用量子模擬器</span><span class="sxs-lookup"><span data-stu-id="3dcac-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="3dcac-129">在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中，會示範三種將 Q# 程式碼傳遞至量子模擬器的方式：</span><span class="sxs-lookup"><span data-stu-id="3dcac-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="3dcac-130">使用命令列</span><span class="sxs-lookup"><span data-stu-id="3dcac-130">Using the command line</span></span>
* <span data-ttu-id="3dcac-131">使用 Python 主機程式</span><span class="sxs-lookup"><span data-stu-id="3dcac-131">Using a Python host program</span></span>
* <span data-ttu-id="3dcac-132">使用 C# 主機程式</span><span class="sxs-lookup"><span data-stu-id="3dcac-132">Using a C# host program</span></span>

<span data-ttu-id="3dcac-133">量子機器是一般 .NET 類別的執行個體，因此可藉由叫用其建構函式來加以建立，就和任何 .NET 類別一樣。</span><span class="sxs-lookup"><span data-stu-id="3dcac-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="3dcac-134">執行此動作的方式取決於您執行 Q# 程式的方式。</span><span class="sxs-lookup"><span data-stu-id="3dcac-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dcac-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3dcac-135">Next steps</span></span>

* <span data-ttu-id="3dcac-136">如需如何在不同環境中的 Q# 程式叫用目標機器的詳細資訊，請參閱 [ 種方式來執行 Q# 程式 ](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="3dcac-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
