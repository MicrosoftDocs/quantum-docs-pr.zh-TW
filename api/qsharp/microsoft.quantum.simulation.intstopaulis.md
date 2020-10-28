---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697146"
---
# <a name="intstopaulis-function"></a>IntsToPaulis 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將整數陣列轉換成單一量子位 Pauli 運算子的陣列。

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>輸入

### <a name="ints--int"></a>int： [int](xref:microsoft.quantum.lang-ref.int)[]

要轉換成 Pauli 運算子之範圍中的整數陣列 `0..3`  。



## <a name="output--pauli"></a>輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`Pauli 運算子 `Pauli[]` 的陣列，其長度等同 `ints` `paulis[idxPauli]` 于 `[PauliI, PauliX, PauliY, PauliZ]` 指定 `ints[idxPauli]` 的專案。