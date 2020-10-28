---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699649"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將中所有詞彙的係數相乘 `GeneratorSystem` 。

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="multiplier--double"></a>乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

係數上的乘數。


### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

要相乘的 `GeneratorSystem`。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

， `GeneratorSystem` 代表係數較大的系統 `multiplier` 。

## <a name="see-also"></a>另請參閱

- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)