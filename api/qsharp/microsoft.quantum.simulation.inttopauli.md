---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229200"
---
# <a name="inttopauli-function"></a>IntToPauli 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將整數轉換成單一量子位的 Pauli 運算子。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>輸入

### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`要轉換成 Pauli 運算子的範圍中的整數。



## <a name="output--pauli"></a>輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`提供的運算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。