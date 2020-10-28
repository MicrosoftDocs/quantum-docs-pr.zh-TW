---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700098"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


無警示幅度放大（依 oracle 進行部分反射）。

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="phases--reflectionphases"></a>階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的階段


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

單一 oracle $A $ 可準備輔助啟動狀態


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

單一 oracle $O $ 的型別 `ObliviousOracle` ，在輔助和系統註冊上共同運作


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

單一量子位旗標登錄的索引



## <a name="output--qubitqubit--unit-adj--ctl"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

根據部分反射來實行無警示振幅放大的作業。

## <a name="remarks"></a>備註

如此一來，就能在的輔助啟動和目標狀態形式上產生更嚴格的條件，而不是 `AmpAmpObliviousByReflectionPhases` 。
假設 $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ 可 \_ 從計算基礎 $ \ket {0} \_ f\ket $ 準備輔助啟動狀態 $ \ket{\text{start}} {fa} $ {0} 。
假設目標狀態是以 $ \ket {1} \_ f $ 標示。
假設 \begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {任何}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 針對某些單一 $U $。