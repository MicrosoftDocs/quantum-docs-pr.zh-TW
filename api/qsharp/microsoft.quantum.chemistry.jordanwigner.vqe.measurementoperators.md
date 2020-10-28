---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698354"
---
# <a name="measurementoperators-function"></a>MeasurementOperators 函式

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

包： [](https://nuget.org/packages/)


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