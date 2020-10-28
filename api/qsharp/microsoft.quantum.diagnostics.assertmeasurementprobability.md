---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698154"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


以指定的 Pauli 為基礎來測量指定量子位的判斷提示，在部分容錯範圍內會有給定機率的指定結果。

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a>輸入

### <a name="bases--pauli"></a>基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要在其上進行判斷提示的註冊。


### <a name="result--__invalidresult__"></a>結果： __無效 <Result>__

的預期結果 `Measure(bases, qubits)` 。


### <a name="prob--double"></a>prob： [Double](xref:microsoft.quantum.lang-ref.double)

預期指定結果的機率。


### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

判斷提示失敗時要報告的訊息。


### <a name="tol--double"></a>tol： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。

## <a name="see-also"></a>另請參閱

- [AssertMeasurement。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)