---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700366"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="fb86b-102">AdiabaticStateEnergyUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="fb86b-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="fb86b-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fb86b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fb86b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb86b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb86b-105">藉由 `statePrepUnitary` 在輸入狀態上套用，然後使用來 adiabatic 狀態準備，最後是使用 `adiabaticUnitary` 來 `qpeUnitary` 對產生的狀態相關的階段估計，來執行狀態準備 `phaseEstAlgorithm` 。</span><span class="sxs-lookup"><span data-stu-id="fb86b-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="fb86b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fb86b-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="fb86b-107">statePrepUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb86b-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fb86b-108">代表初始 dynamical 產生器之狀態準備的 oracle。</span><span class="sxs-lookup"><span data-stu-id="fb86b-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="fb86b-109">adiabaticUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb86b-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fb86b-110">代表 adiabatic 演進演算法的 oracle，此演算法會用來將掃量視為演算法的最終狀態。</span><span class="sxs-lookup"><span data-stu-id="fb86b-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="fb86b-111">qpeUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fb86b-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="fb86b-112">Oracle 代表單一運算子 $U $ 代表時間 $ \delta t $ 在 dynamical 產生器下的時間 $ \ket{\phi} $ 和地面狀態能源 $E = \phi \\ ，\delta t $。</span><span class="sxs-lookup"><span data-stu-id="fb86b-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="fb86b-113">phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb86b-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="fb86b-114">在指定的單一作業上執行階段估計的作業。</span><span class="sxs-lookup"><span data-stu-id="fb86b-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="fb86b-115">如需詳細資訊，請參閱 [反復的階段估計](/quantum/libraries/characterization#iterative-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="fb86b-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fb86b-116">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fb86b-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fb86b-117">要用來執行模擬的量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="fb86b-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="fb86b-118">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb86b-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb86b-119">由 $U $ 所代表之產生器的接地 $ \hat{\phi} $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="fb86b-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>