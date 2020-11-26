---
uid: Microsoft.Quantum.Arithmetic.Carry
title: 執行操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223590"
---
# <a name="carry-operation"></a>執行操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


會執行可還原的執行閘道。 給定量子位中編碼的執行位 `carryIn` 和在和中編碼的兩個被加數位 `summand1` `summand2` ，會計算中的位 xor `carryIn` ， `summand1` 而 `summand2` 在量子位中則 `summand2` 會進行 xor 至量子位 `carryOut` 。

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="carryin--qubit"></a>carryIn： [量子位](xref:microsoft.quantum.lang-ref.qubit)

執行量子位。


### <a name="summand1--qubit"></a>summand1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個被加數量子位。


### <a name="summand2--qubit"></a>summand2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第二個被加數量子位，會取代為和總和的低位 `summand1` `summand2` 。


### <a name="carryout--qubit"></a>carryOut： [量子位](xref:microsoft.quantum.lang-ref.qubit)

執行量子位，將會以較高的總和位進行 xor。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

