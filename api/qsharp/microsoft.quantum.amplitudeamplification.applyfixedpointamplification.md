---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700119"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="d7bed-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="d7bed-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="d7bed-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d7bed-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d7bed-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7bed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7bed-105">Fixed-Point 振幅放大演算法</span><span class="sxs-lookup"><span data-stu-id="d7bed-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d7bed-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d7bed-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="d7bed-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="d7bed-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="d7bed-108">準備開始狀態的單一 oracle。</span><span class="sxs-lookup"><span data-stu-id="d7bed-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="d7bed-109">startQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d7bed-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d7bed-110">量子位註冊</span><span class="sxs-lookup"><span data-stu-id="d7bed-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7bed-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7bed-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d7bed-112">備註</span><span class="sxs-lookup"><span data-stu-id="d7bed-112">Remarks</span></span>

<span data-ttu-id="d7bed-113">StartQubits 必須是 $ \ket{0 \cdots 0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="d7bed-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="d7bed-114">這項作業會逐一查看多個 $2 $ 的查詢，直到達到最大的查詢數目，或找到目標狀態為止。</span><span class="sxs-lookup"><span data-stu-id="d7bed-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>