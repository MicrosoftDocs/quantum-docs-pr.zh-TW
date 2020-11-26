---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191511"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification 操作

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


藉由指定部分反射來無警示振幅放大。

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="phases--reflectionphases"></a>階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的階段


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

輔助暫存器開始狀態的反映運算子


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

關於輔助暫存器目標狀態的反映運算子


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

單一 oracle $O $ 的型別 `ObliviousOracle` ，會在輔助和系統註冊上共同運作。


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

輔助暫存器


### <a name="systemregister--qubit"></a>systemRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

系統註冊



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

給定特定的輔助啟動狀態 $ \ket{\text{start}} \_ a $，特定的輔助目標狀態 $ \ket{\text{target}} \_ a $，以及任何系統狀態 $ \ket{\psi} \_ s $，假設 \begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} \_ a\cdots \end{align} 的部分單一 $U $。
依應用程式和其 adjoint 在輔助暫存器上開始和目標狀態的一系列反映 `signalOracle` ，可能會改變套用 U 的成功機率。

在大部分情況下， `auxiliaryRegister` 會以 $ \ket{\text{start}} a $ 的狀態初始化 \_ 。

## <a name="references"></a>參考

請參閱

- [ *D.W. Berry、am Childs、Cleve、Kothari、R.D. Somma （*](https://arxiv.org/abs/1312.1414) 適用于標準版本）。
  請參閱
- [ *G.H. Low、I.L. Chuang*](https://arxiv.org/abs/1610.06546) for 一般化至部分反射。