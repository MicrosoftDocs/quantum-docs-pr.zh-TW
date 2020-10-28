---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700875"
---
# <a name="getgeneratorsystemfunction-function"></a>GetGeneratorSystemFunction 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


抓取 `GeneratorIndex` 中的函數 `GeneratorSystem` 。

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a>輸入

### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

重要的 `GeneratorSystem`。



## <a name="output--int---generatorindex"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

在 Hamiltonian 中為每個詞彙編制索引的函式 `GeneratorIndex` 。

## <a name="see-also"></a>另請參閱

- [GeneratorIndex。](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)