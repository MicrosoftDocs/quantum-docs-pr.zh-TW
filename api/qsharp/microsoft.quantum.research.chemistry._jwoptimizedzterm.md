---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: _JWOptimizedZTerm 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: fe68295748759a25c52f8e3c2efbc7570c9dcc1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848051"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="aaca5-102">_JWOptimizedZTerm 操作</span><span class="sxs-lookup"><span data-stu-id="aaca5-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="aaca5-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="aaca5-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="aaca5-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="aaca5-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="aaca5-105">依所述的 Z 詞彙套用時間演進 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="aaca5-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aaca5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="aaca5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="aaca5-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="aaca5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="aaca5-108">`GeneratorIndex` 代表 Z 詞彙。</span><span class="sxs-lookup"><span data-stu-id="aaca5-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="aaca5-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaca5-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aaca5-110">時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="aaca5-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="aaca5-111">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aaca5-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aaca5-112">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="aaca5-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="aaca5-113">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aaca5-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aaca5-114">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="aaca5-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aaca5-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aaca5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

