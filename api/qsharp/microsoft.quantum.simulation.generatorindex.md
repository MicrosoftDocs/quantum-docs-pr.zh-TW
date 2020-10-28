---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700690"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="d4d0b-102">GeneratorIndex 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d4d0b-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="d4d0b-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d4d0b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d4d0b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4d0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4d0b-105">代表所有 dynamical 產生器集合中的單一基本詞彙，例如 Hermitian 運算子，該產生器會有從該產生器到時間演進的對應 `EvolutionSet` 。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="d4d0b-106">第一個元素 (Int []，Double [] ) 是單一詞彙的索引，例如，使用係數0.5 的 Pauli 字串 XXY 會依 ( [1，1，2]，[0.5] ) 進行編制索引。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="d4d0b-107">或者，以連續變數（例如 X cos φ + Y sin φ）參數化的 Hamiltonian，可能會以 ( []，[φ] ) 來表示。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="d4d0b-108">第二個元素會編制產生器作用所在的子系統。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="d4d0b-109">備註</span><span class="sxs-lookup"><span data-stu-id="d4d0b-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d4d0b-110">`GeneratorIndex`除了參考特定的產生器集之外，未定義的解讀。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4d0b-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4d0b-111">See Also</span></span>

- [<span data-ttu-id="d4d0b-112">EvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="d4d0b-113">PauliEvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="d4d0b-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)