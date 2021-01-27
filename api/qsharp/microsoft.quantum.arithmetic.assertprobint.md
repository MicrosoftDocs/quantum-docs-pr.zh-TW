---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843412"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>範例

假設註冊會 `qubits` 以位元組由小到大的格式，將3量子位的量子狀態 $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {6} $ 編碼。
這表示 number 狀態 $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ 和 $ \ket {6} \equiv\ket {0} \ket {1} \ket {1} $。 然後，下列判斷提示會成功：

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```