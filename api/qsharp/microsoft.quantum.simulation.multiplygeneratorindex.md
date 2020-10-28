---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700858"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將中的係數相乘 `GeneratorIndex` 。

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="multiplier--double"></a>乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

係數上的乘數。


### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

要相乘的 `GeneratorIndex`。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

， `GeneratorIndex` 表示具有較大係數的詞彙 `multiplier` 。

## <a name="see-also"></a>另請參閱

- [GeneratorIndex。](xref:Microsoft.Quantum.Simulation.GeneratorIndex)