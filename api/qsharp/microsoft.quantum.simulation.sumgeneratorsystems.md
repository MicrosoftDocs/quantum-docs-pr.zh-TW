---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192463"
---
# <a name="sumgeneratorsystems-function"></a>SumGeneratorSystems 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


新增多個 `GeneratorSystem` 來建立新的 GeneratorSystem。

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="generatorsystems--generatorsystem"></a>generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]

類型為 `GeneratorSystem[]` 的陣列。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。

## <a name="see-also"></a>另請參閱

- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)