---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 總和運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699527"
---
# <a name="sum-operation"></a>總和運算

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


實行可還原的總和閘道。 給定量子位中編碼的執行位 `carryIn` 和在和中編碼的兩個被加數位時 `summand1` ，會 `summand2` `carryIn` `summand1` `summand2` 在量子位中計算的位 xor 和 `summand2` 。

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="carryin--qubit"></a>carryIn： [量子位](xref:microsoft.quantum.lang-ref.qubit)

執行量子位。


### <a name="summand1--qubit"></a>summand1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個被加數量子位。


### <a name="summand2--qubit"></a>summand2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第二個被加數量子位，會取代為和總和的低位 `summand1` `summand2` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

相對於作業 `Carry` ，這不會計算執行時位。