---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226990"
---
# <a name="multim-operation"></a>MultiM 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以標準為單位測量指定陣列中的每個量子位。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>輸入

### <a name="targets--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的量子位陣列。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__ 的 []

測量結果的陣列。