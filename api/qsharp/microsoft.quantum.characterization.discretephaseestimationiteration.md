---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 03e2300dcc2d2cb42992e074833c8cd2530e898b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839963"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="80ccc-102">DiscretePhaseEstimationIteration 操作</span><span class="sxs-lookup"><span data-stu-id="80ccc-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="80ccc-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="80ccc-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="80ccc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80ccc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80ccc-105">使用單一 oracle 的整數乘冪，執行反復 (傳統方式控制) 階段估計演算法的單一反復專案。</span><span class="sxs-lookup"><span data-stu-id="80ccc-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="80ccc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="80ccc-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="80ccc-107">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="80ccc-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="80ccc-108">以整數和暫存器為目標的作業，例如 $U ^ m $ 會套用至指定的暫存器，其中 $U $ 是要預估其階段的單一位置，而 $m $ 是指定給 oracle 的整數乘冪</span><span class="sxs-lookup"><span data-stu-id="80ccc-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="80ccc-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80ccc-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80ccc-110">要套用指定之單一 oracle 的次數。</span><span class="sxs-lookup"><span data-stu-id="80ccc-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="80ccc-111">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="80ccc-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="80ccc-112">在對目標狀態採取行動之前，用來將控制項量子位上的階段反轉的角度。</span><span class="sxs-lookup"><span data-stu-id="80ccc-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="80ccc-113">targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="80ccc-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="80ccc-114">註冊指定的單一 oracle 所採取的狀態。</span><span class="sxs-lookup"><span data-stu-id="80ccc-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="80ccc-115">controlQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="80ccc-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="80ccc-116">用來控制指定 oracle 之應用程式的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="80ccc-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80ccc-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80ccc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

