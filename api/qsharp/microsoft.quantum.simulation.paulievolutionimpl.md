---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229132"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="8f8c8-102">PauliEvolutionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="8f8c8-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="8f8c8-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8f8c8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8f8c8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f8c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f8c8-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="8f8c8-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="8f8c8-106">如需詳細資料，請參閱 Dynamical 產生器 [模型](/quantum/libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="8f8c8-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8f8c8-107">輸入</span><span class="sxs-lookup"><span data-stu-id="8f8c8-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="8f8c8-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8f8c8-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8f8c8-109">以 Pauli 為基礎的單一演進所呈現的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="8f8c8-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="8f8c8-110">delta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f8c8-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f8c8-111">中所參考之詞彙在時間演進期間的乘數 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="8f8c8-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8f8c8-112">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8f8c8-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8f8c8-113">依照時間演進運算子註冊。</span><span class="sxs-lookup"><span data-stu-id="8f8c8-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f8c8-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f8c8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

