---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699667"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

包： [](https://nuget.org/packages/)


指定多量子位 Pauli 運算子的陣列時，會使用指定的測量小工具來測量每個運算子，然後傳回結果的陣列。

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

要測量的多量子位 Pauli 運算子的陣列。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊要測量指定運算子的。


### <a name="gadget--pauliqubit--__invalidresult__"></a>小工具： ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]， [量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => __無效 <Result>__ 

執行指定多量子位運算子測量的作業。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__ 的 []

從測量的每個專案所取得的結果 `paulis` 陣列 `target` 。