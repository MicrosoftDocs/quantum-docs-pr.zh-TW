---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859134"
---
# <a name="applyunitary-operation"></a>ApplyUnitary 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


套用 2 ^ n x 2 ^ n 個單一矩陣所定義的閘道。

如果矩陣不是單一或大小錯誤，則會失敗。

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="unitary--complex"></a>單一： [複雜](xref:Microsoft.Quantum.Math.Complex)[] []

描述作業的 2 ^ n x 2 ^ n 個單一矩陣。
如果矩陣不是單一或不適合的大小，則會擲回例外狀況。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用作業的量子位（長度為 n 的註冊）。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

