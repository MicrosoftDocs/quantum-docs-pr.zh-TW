---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854617"
---
# <a name="settobasisstate-operation"></a>SetToBasisState 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


藉由測量量子位並視需要套用位翻轉，將量子位設定為指定的計算基礎狀態。

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="desired--__invalidresult__"></a>需要：__無效 <Result>__

應設定量子位的基礎狀態。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要設定其狀態的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這項作業的非變異， `M(q)` 會在之後立即呼叫 `SetToBasisState(result, q)` `result` 。