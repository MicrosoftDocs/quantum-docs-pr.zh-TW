---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697610"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

包： [](https://nuget.org/packages/)


以 Pauli Z 為單位共同測量量子位的暫存器。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>描述

以 $Z \otimes Z \otimes \cdots \otimes Z $ 基礎測量量子位的暫存器，代表整個登錄的同位檢查。

## <a name="input"></a>輸入

### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的註冊。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__

測量 $Z \otimes Z \otimes \cdots \otimes Z $ 的結果。