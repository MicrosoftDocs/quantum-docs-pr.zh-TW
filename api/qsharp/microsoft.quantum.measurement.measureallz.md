---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854679"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以 Pauli Z 為單位共同測量量子位的暫存器。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>描述

以 $Z \otimes Z \otimes \cdots \otimes Z $ 基礎測量量子位的暫存器，代表整個登錄的同位檢查。

## <a name="input"></a>輸入

### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的註冊。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

測量 $Z \otimes Z \otimes \cdots \otimes Z $ 的結果。