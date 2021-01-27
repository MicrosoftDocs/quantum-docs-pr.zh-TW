---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853777"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定多量子位 Pauli 運算子的陣列時，會使用指定的測量小工具來測量每個運算子，然後傳回結果的陣列。

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

要測量的多量子位 Pauli 運算子的陣列。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊要測量指定運算子的。


### <a name="gadget--pauliqubit--__invalidresult__"></a>小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__無效 <Result>__ 

執行指定多量子位運算子測量的作業。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__ 的 []

從測量的每個專案所取得的結果 `paulis` 陣列 `target` 。