---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699947"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


判斷量子暫存器特定狀態的機率具有預期的值。

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>描述

假設有 $n $-量子位量子 state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ Alpha_j \ket{j} $，判斷提示 $ \ket{j} $j $ 的機率 $ | \ Alpha_j | ^ 2 $ 具有預期的值。

## <a name="input"></a>輸入

### <a name="stateindex--int"></a>stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)

索引 $j $ 表示由暫存器表示的狀態 $ \ket{j} $ `LittleEndian` 。


### <a name="expected--double"></a>預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$ | \ Alpha_j | ^ 2 $ 的預期值。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的格式儲存 $ \ket{\psi} $ 的量子位暫存器。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

實際和預期之間差異的絕對容錯。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

