---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: d6e8f7085cf0558960d055dbeeb08740c3fab049
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229659"
---
# <a name="addgeneratorsystems-function"></a>AddGeneratorSystems 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


新增兩個 `GeneratorSystem` 來建立新的 `GeneratorSystem` 。

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="generatorsystema--generatorsystem"></a>generatorSystemA： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

第一個 `GeneratorSystem`。


### <a name="generatorsystemb--generatorsystem"></a>generatorSystemB： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

第二個 `GeneratorSystem`。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。

## <a name="see-also"></a>另請參閱

- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)