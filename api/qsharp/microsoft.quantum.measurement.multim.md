---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697599"
---
# <a name="multim-operation"></a>MultiM 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

包： [](https://nuget.org/packages/)


以標準為單位測量指定陣列中的每個量子位。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>輸入

### <a name="targets--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的量子位陣列。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__ 的 []

測量結果的陣列。