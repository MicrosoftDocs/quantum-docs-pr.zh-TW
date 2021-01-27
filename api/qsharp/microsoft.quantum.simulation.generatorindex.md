---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858373"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="66c0a-102">GeneratorIndex 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="66c0a-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="66c0a-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="66c0a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="66c0a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66c0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66c0a-105">代表所有 dynamical 產生器集合中的單一基本詞彙，例如 Hermitian 運算子，該產生器會有從該產生器到時間演進的對應 `EvolutionSet` 。</span><span class="sxs-lookup"><span data-stu-id="66c0a-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="66c0a-106">第一個元素 (Int []，Double [] ) 是單一詞彙的索引，例如，使用係數0.5 的 Pauli 字串 XXY 會依 ( [1，1，2]，[0.5] ) 進行編制索引。</span><span class="sxs-lookup"><span data-stu-id="66c0a-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="66c0a-107">或者，以連續變數（例如 X cos φ + Y sin φ）參數化的 Hamiltonian，可能會以 ( []，[φ] ) 來表示。</span><span class="sxs-lookup"><span data-stu-id="66c0a-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="66c0a-108">第二個元素會編制產生器作用所在的子系統。</span><span class="sxs-lookup"><span data-stu-id="66c0a-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="66c0a-109">範例</span><span class="sxs-lookup"><span data-stu-id="66c0a-109">Example</span></span>

<span data-ttu-id="66c0a-110">使用  <xref:microsoft.quantum.simulation.paulievolutionset> 運算子 $ \pi X_2 X_5 Y_9 $ 表示為：</span><span class="sxs-lookup"><span data-stu-id="66c0a-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="66c0a-111">備註</span><span class="sxs-lookup"><span data-stu-id="66c0a-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="66c0a-112">`GeneratorIndex`除了參考特定的產生器集之外，未定義的解讀。</span><span class="sxs-lookup"><span data-stu-id="66c0a-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="66c0a-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66c0a-113">See Also</span></span>

- [<span data-ttu-id="66c0a-114">EvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="66c0a-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="66c0a-115">PauliEvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="66c0a-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)