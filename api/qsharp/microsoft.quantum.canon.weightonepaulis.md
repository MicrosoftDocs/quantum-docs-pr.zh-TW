---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204533"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回指定量子位數目之所有加權 1 Pauli 運算子的陣列。

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

用來定義所傳回 Pauli 運算子的量子位數目。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

多量子位 Pauli 運算子的陣列，其中每個運算子都會表示為具有長度的陣列 `nQubits` 。