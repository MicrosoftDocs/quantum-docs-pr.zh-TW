---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852333"
---
# <a name="permutequbits-operation"></a>PermuteQubits 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用交換操作來 Permutes 量子位。

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="ordering--int"></a>順序： [Int](xref:microsoft.quantum.lang-ref.int)[]

描述量子位的新順序，其中量子位 at index 現在會依序為 [i]。


### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要處理的量子位 register。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

給定順序 = [2，1，0]，並註冊 $ \ket{\ Alpha_0} \ket{\ Alpha_1} \ket{\ Alpha_2} $，PermuteQubits 將註冊變更為 $ \ket{\ Alpha_2} \ket{\ Alpha_1} \ket{\ Alpha_0} $

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```