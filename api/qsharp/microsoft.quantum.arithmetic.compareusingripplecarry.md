---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843278"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


這項作業會測試量子位暫存器所代表的整數是否大於另一個整數，並將結果的 XOR 套用至輸出量子位。

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

如果有兩個整數， `x` 並 `y` 儲存在大小相同的量子位暫存器中，此作業就會檢查它們是否符合 `x > y` 。 若為 true，則會將1進行 xor 成輸出量子位。 否則，會將0進行 xor 到輸出量子位中。
換句話說，這項作業可以用單一 $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y) } 來表示。
\end{align} $ $

## <a name="input"></a>輸入

### <a name="x--littleendian"></a>x： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要在量子位暫存器中以格式儲存的第一個數位 `LittleEndian` 。


### <a name="y--littleendian"></a>y： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要在量子位暫存器中以格式儲存的第二個數字 `LittleEndian` 。


### <a name="output--qubit"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)

儲存比較 $x 結果>y $ 的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考資料

- 新的量子 ripple-攜帶加法斷路 Steven A. Cuccaro、Thomas G. Draper、Samuel A. Kutin、David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184