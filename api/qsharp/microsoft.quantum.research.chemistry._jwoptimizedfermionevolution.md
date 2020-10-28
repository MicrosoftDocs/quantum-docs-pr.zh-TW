---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700374"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="9b568-102">_JWOptimizedFermionEvolution 操作</span><span class="sxs-lookup"><span data-stu-id="9b568-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="9b568-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="9b568-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="9b568-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b568-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b568-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 JWOptimized 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="9b568-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="9b568-106">如需詳細資料，請參閱 Dynamical 產生器 [模型](../libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="9b568-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9b568-107">輸入</span><span class="sxs-lookup"><span data-stu-id="9b568-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="9b568-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9b568-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9b568-109">以 JWOptimized 為基礎的單一演進所呈現的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="9b568-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9b568-110">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b568-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b568-111">中所參考之詞彙在時間演進期間的乘數 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="9b568-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="9b568-112">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b568-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b568-113">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="9b568-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9b568-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b568-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b568-115">依照時間演進運算子註冊。</span><span class="sxs-lookup"><span data-stu-id="9b568-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b568-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b568-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

