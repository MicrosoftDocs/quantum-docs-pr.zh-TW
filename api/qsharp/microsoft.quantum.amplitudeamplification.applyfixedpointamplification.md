---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191528"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification 操作

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fixed-Point 振幅放大演算法

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="statepreporacle--stateoracle"></a>statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

準備開始狀態的單一 oracle。


### <a name="startqubits--qubit"></a>startQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位註冊



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

StartQubits 必須是 $ \ket{0 \cdots 0} $ 狀態。 這項作業會逐一查看多個 $2 $ 的查詢，直到達到最大的查詢數目，或找到目標狀態為止。