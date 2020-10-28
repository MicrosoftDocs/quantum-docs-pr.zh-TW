---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700959"
---
# <a name="inttopauli-function"></a>IntToPauli 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將整數轉換成單一量子位的 Pauli 運算子。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>輸入

### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`要轉換成 Pauli 運算子的範圍中的整數。



## <a name="output--pauli"></a>輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`提供的運算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。