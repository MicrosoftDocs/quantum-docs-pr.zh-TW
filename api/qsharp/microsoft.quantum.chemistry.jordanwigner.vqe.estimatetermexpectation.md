---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835677"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation 操作

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


計算與指定 Jordan-Wigner Hamiltonian 期限相關聯的能源

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>描述

這項作業會評估與每個測量運算子相關聯的預期值，並使用取樣來乘以對應的係數。
結果會匯總到包含 Jordan-Wigner 期限能源的變數中。

## <a name="input"></a>輸入

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

用於狀態準備的單一。


### <a name="ops--pauli"></a>ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Jordan-Wigner 詞彙的測量運算子。


### <a name="coeffs--double"></a>coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner 詞彙的係數。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

模擬分子系統所需的量子位數目。


### <a name="nsamples--int"></a>nSamples： [Int](xref:microsoft.quantum.lang-ref.int)

要用於估計預期詞彙的樣本數目。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

與 Jordan-Wigner 詞彙相關聯的能源。