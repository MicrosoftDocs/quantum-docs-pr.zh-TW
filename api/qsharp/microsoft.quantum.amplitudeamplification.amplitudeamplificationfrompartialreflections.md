---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700131"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a>AmplitudeAmplificationFromPartialReflections 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


部分反射的波幅放大。

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="phases--reflectionphases"></a>階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的階段


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

關於開始狀態的反映運算子


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

目標狀態的反映運算子



## <a name="output--qubit--unit-adj--ctl"></a>Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

以部分反射來執行幅度放大的運算。

## <a name="remarks"></a>備註

振幅放大是無警示振幅放大的特殊案例，其中沒有系統量子位，且無警示 oracle 設定為 identity。
在大部分情況下， `startQubits` 會在狀態 $ \ket{\text{start}} $1 中初始化 \_ ，也就是的 $-$1 eigenstate `startStateReflection` 。