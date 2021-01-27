---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825762"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


測量一組指定的穩定產生器群組。

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>輸入

### <a name="stabilizergroup--pauli"></a>stabilizerGroup： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Multiqubit Pauli 運算子的陣列。
例如， `stabilizerGroup[0]` 是單一量子位 Pauli 矩陣的清單，其 tensor 產品是一個穩定器產生器。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定義了穩定程式碼的量子位陣列。


### <a name="gadget--pauliqubit--__invalidresult__"></a>小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__無效 <Result>__ 

指定如何測量 multiqubit Pauli 運算子的作業。



## <a name="output--syndrome"></a>輸出： [症狀](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

度量的結果。

## <a name="remarks"></a>備註

這不會檢查指定的產生器集是否通勤。
如果未通勤，測量結果可能是任意的。