---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d9f0d17c091ae771702e4047d17e1769d6bb294
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700187"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="ec0c1-102">_JWOptimizedPQandPQQRTerm 操作</span><span class="sxs-lookup"><span data-stu-id="ec0c1-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="ec0c1-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="ec0c1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec0c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec0c1-105">依所述的 PQ 或 PQQR 詞彙套用時間演進 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ec0c1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ec0c1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ec0c1-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ec0c1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ec0c1-108">`GeneratorIndex` 代表 PQ 或 PQQr 詞彙。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ec0c1-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec0c1-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec0c1-110">時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="ec0c1-111">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ec0c1-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ec0c1-112">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ec0c1-113">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec0c1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ec0c1-114">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="ec0c1-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec0c1-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec0c1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

