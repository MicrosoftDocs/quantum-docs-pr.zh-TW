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
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex 使用者定義型別

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


代表所有 dynamical 產生器集合中的單一基本詞彙，例如 Hermitian 運算子，該產生器會有從該產生器到時間演進的對應 `EvolutionSet` 。

第一個元素 (Int []，Double [] ) 是單一詞彙的索引，例如，使用係數0.5 的 Pauli 字串 XXY 會依 ( [1，1，2]，[0.5] ) 進行編制索引。 或者，以連續變數（例如 X cos φ + Y sin φ）參數化的 Hamiltonian，可能會以 ( []，[φ] ) 來表示。 第二個元素會編制產生器作用所在的子系統。

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>備註

> [!WARNING]
> `GeneratorIndex`除了參考特定的產生器集之外，未定義的解讀。

## <a name="see-also"></a>另請參閱

- [EvolutionSet。](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [PauliEvolutionSet。](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)