---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847224"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="e4076-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="e4076-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="e4076-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e4076-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e4076-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4076-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4076-105">Fixed-Point 振幅放大演算法</span><span class="sxs-lookup"><span data-stu-id="e4076-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e4076-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e4076-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="e4076-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e4076-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e4076-108">準備開始狀態的單一 oracle。</span><span class="sxs-lookup"><span data-stu-id="e4076-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="e4076-109">startQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4076-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4076-110">量子位註冊</span><span class="sxs-lookup"><span data-stu-id="e4076-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4076-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4076-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e4076-112">備註</span><span class="sxs-lookup"><span data-stu-id="e4076-112">Remarks</span></span>

<span data-ttu-id="e4076-113">StartQubits 必須是 $ \ket{0 \cdots 0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="e4076-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="e4076-114">這項作業會逐一查看多個 $2 $ 的查詢，直到達到最大的查詢數目，或找到目標狀態為止。</span><span class="sxs-lookup"><span data-stu-id="e4076-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>