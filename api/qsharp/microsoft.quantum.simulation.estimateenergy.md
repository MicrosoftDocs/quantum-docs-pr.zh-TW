---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700162"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="2a1e7-102">EstimateEnergy 操作</span><span class="sxs-lookup"><span data-stu-id="2a1e7-102">EstimateEnergy operation</span></span>

<span data-ttu-id="2a1e7-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2a1e7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a1e7-105">藉由在自動設定的 `statePrepUnitary` 輸入狀態階段估計上套用，並針對使用的 `qpeUnitary` 結果狀態套用，以執行狀態準備 `phaseEstAlgorithm` 。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="2a1e7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2a1e7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2a1e7-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a1e7-108">用來執行模擬的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="2a1e7-109">statePrepUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2a1e7-110">代表初始 dynamical 產生器之狀態準備的 oracle。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="2a1e7-111">qpeUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2a1e7-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2a1e7-112">Oracle 代表單一運算子 $U $ 代表時間 $ \delta t $ 在 dynamical 產生器下的時間 $ \ket{\phi} $ 和地面狀態能源 $E = \phi \\ ，\delta t $。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="2a1e7-113">phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="2a1e7-114">在指定的單一作業上執行階段估計的作業。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="2a1e7-115">如需詳細資訊，請參閱 [反復的階段估計](/quantum/libraries/characterization#iterative-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="2a1e7-116">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a1e7-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a1e7-117">以 $U $ 表示之產生器的接地狀態能源 $ \phi $ 的預估 $ \hat{\phi} $。</span><span class="sxs-lookup"><span data-stu-id="2a1e7-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>