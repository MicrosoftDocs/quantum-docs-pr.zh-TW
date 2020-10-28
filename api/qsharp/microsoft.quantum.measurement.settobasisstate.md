---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700910"
---
# <a name="settobasisstate-operation"></a>SetToBasisState 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

包： [](https://nuget.org/packages/)


藉由測量量子位並視需要套用位翻轉，將量子位設定為指定的計算基礎狀態。

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="desired--__invalidresult__"></a>需要： __無效 <Result>__

應設定量子位的基礎狀態。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要設定其狀態的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這項作業的非變異， `M(q)` 會在之後立即呼叫 `SetToBasisState(result, q)` `result` 。