---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853440"
---
# <a name="assertqubitwithintolerance-operation"></a>AssertQubitWithinTolerance 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


判斷提示量子位 `q` 是在預期的 Pauli Z 運算子 eigenstate 中，直到指定的容錯。

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>輸入

### <a name="expected--__invalidresult__"></a>預期：__無效 <Result>__

量子位預期在哪一個狀態： `Zero` 或 `One` 。


### <a name="q--qubit"></a>問： [量子位](xref:microsoft.quantum.lang-ref.qubit)

已判斷提示其狀態的量子位。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

量子位的測量機率傳回預期結果的容錯。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允許判斷提示任意量子位狀態，而不只是 $Z $ eigenstates。

## <a name="see-also"></a>另請參閱

- [AssertQubitIsInStateWithinTolerance。](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)