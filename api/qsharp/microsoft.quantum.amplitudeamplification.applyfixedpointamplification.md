---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191528"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="5ed5a-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="5ed5a-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="5ed5a-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5ed5a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5ed5a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ed5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ed5a-105">Fixed-Point 振幅放大演算法</span><span class="sxs-lookup"><span data-stu-id="5ed5a-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5ed5a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5ed5a-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="5ed5a-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="5ed5a-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="5ed5a-108">準備開始狀態的單一 oracle。</span><span class="sxs-lookup"><span data-stu-id="5ed5a-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="5ed5a-109">startQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5ed5a-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5ed5a-110">量子位註冊</span><span class="sxs-lookup"><span data-stu-id="5ed5a-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ed5a-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ed5a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5ed5a-112">備註</span><span class="sxs-lookup"><span data-stu-id="5ed5a-112">Remarks</span></span>

<span data-ttu-id="5ed5a-113">StartQubits 必須是 $ \ket{0 \cdots 0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="5ed5a-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="5ed5a-114">這項作業會逐一查看多個 $2 $ 的查詢，直到達到最大的查詢數目，或找到目標狀態為止。</span><span class="sxs-lookup"><span data-stu-id="5ed5a-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>