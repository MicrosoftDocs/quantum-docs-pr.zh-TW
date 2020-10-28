---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 50e0c536b01cddb56482580fd634270c4e104173
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700863"
---
# <a name="idxtocoeff-function"></a>IdxToCoeff 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


用於執行 `PauliBlockEncoding`

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a>輸入

### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="genfun--int---generatorindex"></a>genFun： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="genidxtocoeff--generatorindex---double"></a>genIdxToCoeff： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="see-also"></a>另請參閱

- [PauliBlockEncoding。](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)