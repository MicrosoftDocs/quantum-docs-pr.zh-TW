---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: _JWOptimizedZZTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700367"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="c7cf1-102">_JWOptimizedZZTerm 操作</span><span class="sxs-lookup"><span data-stu-id="c7cf1-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="c7cf1-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c7cf1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7cf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7cf1-105">依所述的 ZZ 詞彙套用時間演進 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c7cf1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c7cf1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="c7cf1-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c7cf1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c7cf1-108">`GeneratorIndex` 代表 ZZ 詞彙。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c7cf1-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7cf1-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7cf1-110">時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="c7cf1-111">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c7cf1-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c7cf1-112">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c7cf1-113">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c7cf1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c7cf1-114">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="c7cf1-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7cf1-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7cf1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

