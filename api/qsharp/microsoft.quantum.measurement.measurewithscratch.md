---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699664"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

包： [](https://nuget.org/packages/)


使用明確的臨時量子位來測量指定的 Pauli 運算子，以執行度量。

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]

指定為單一量子位 Pauli 運算子陣列的多量子位 Pauli 運算子。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的量子位暫存器。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__

在註冊上測量指定 Pauli 運算子的結果 `target` 。