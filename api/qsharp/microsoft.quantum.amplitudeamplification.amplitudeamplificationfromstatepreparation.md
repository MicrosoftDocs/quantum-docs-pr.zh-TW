---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191596"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificationFromStatePreparation 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


部分反射的波幅放大（依 oracle）。

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="phases--reflectionphases"></a>階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的階段


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

準備開始狀態的單一 oracle $A $


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

索引至旗標量子位



## <a name="output--qubit--unit--is-adj--ctl"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

一種作業，可由部分反射實作為 oracle 來執行幅度放大。

## <a name="remarks"></a>備註

如此一來，在開始和目標狀態的表單上會產生更嚴格的條件 `AmpAmpByReflectionPhases` 。
假設目標狀態是以 $ \ket {1} \_ f $ 標示。
假設 \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 在大部分的情況下， `flagQubit` 並 `auxiliaryRegister` 在 state $ \ket {0} \_ {f} \ket {0} \_ s $ 中初始化。