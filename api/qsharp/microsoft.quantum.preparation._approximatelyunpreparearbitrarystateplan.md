---
uid: Microsoft.Quantum.Preparation._ApproximatelyUnprepareArbitraryStatePlan
title: _ApproximatelyUnprepareArbitraryStatePlan 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 4050a65b0830da4c3d73e84942780aa7c2643c76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700775"
---
# <a name="_approximatelyunpreparearbitrarystateplan-function"></a>_ApproximatelyUnprepareArbitraryStatePlan 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


任意狀態準備程式的執行步驟。

```qsharp
function _ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>輸入

### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl： [範圍](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit-adj--ctl"></a>Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []



## <a name="see-also"></a>另請參閱

- [PrepareArbitraryState。](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)