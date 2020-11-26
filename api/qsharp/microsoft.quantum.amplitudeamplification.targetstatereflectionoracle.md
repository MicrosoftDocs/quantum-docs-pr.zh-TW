---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191103"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


`ReflectionOracle`針對旗標量子位唯一標示的目標狀態，建立相關的。

目標狀態的單一量子位設為1，其他所有專案0： $ \ket {1} _f $。

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>輸入

### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

量子位 $f $ of oracle 旗標的索引。



## <a name="output--reflectionoracle"></a>輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

`ReflectionOracle`，反映 $ \ket _f $ 所標記的狀態 {1} 。

## <a name="see-also"></a>另請參閱

- [Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)