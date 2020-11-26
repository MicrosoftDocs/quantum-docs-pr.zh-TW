---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214342"
---
# <a name="measurementoperators-function"></a>MeasurementOperators 函式

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


計算計算 Jordan-Wigner 詞彙的預期時，所需的所有測量運算子。

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

模擬分子系統所需的量子位數目。


### <a name="indices--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)[]

陣列，其中包含每個 Pauli 運算子適用的量子位索引。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner 詞彙的型別。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

度量運算子的陣列 (每個都是 Pauli) 的陣列。