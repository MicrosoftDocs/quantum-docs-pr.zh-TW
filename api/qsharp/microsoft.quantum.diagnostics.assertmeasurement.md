---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853493"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


以指定的 Pauli 為基礎測量指定量子位的判斷提示，一定會有指定的結果。

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="bases--pauli"></a>基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要在其上進行判斷提示的註冊。


### <a name="result--__invalidresult__"></a>結果：__無效 <Result>__

的預期結果 `Measure(bases, qubits)` 。


### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

判斷提示失敗時要報告的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。

## <a name="see-also"></a>另請參閱

- [AssertMeasurementProbability。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)