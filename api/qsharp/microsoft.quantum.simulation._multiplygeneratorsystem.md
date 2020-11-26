---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: _MultiplyGeneratorSystem 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 9fdc52bdea69e9507510a51be258eaba8e61f673
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229676"
---
# <a name="_multiplygeneratorsystem-function"></a>_MultiplyGeneratorSystem 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將中所有詞彙的係數相乘 `GeneratorSystem` 。

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="multiplier--double"></a>乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)




### <a name="idxterm--int"></a>idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)





## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)



## <a name="remarks"></a>備註

這是中繼步驟，不應該呼叫。