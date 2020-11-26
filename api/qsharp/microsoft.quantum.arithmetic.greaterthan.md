---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223080"
---
# <a name="greaterthan-operation"></a>GreaterThan 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在編碼為量子位暫存器的兩個整數之間套用大於比較，並根據比較結果來翻轉目標量子位。

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

執行嚴格大於兩個整數 $x $ 和 $y $ 的比較，在量子位中編碼的是 xs 和 y) 。 如果 $x > y $，則結果量子位將會翻轉，否則結果量子位將會保留其狀態。

## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位會將第一個整數的編碼編碼 $x $。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位會將第二個整數的編碼 $y $。


### <a name="result--qubit"></a>結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)

如果 $x > y $，將會翻轉的單一量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

使用 $x-y = (x ' + y) ' $ 的訣竅，其中 ' 代表一補數。

## <a name="references"></a>參考

- Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener，聖馬丁 Roetteler，Krysta M. Svore： "使用 2n + 2 量子位搭配 Toffoli 型模組化乘法進行分解"，2016 https://arxiv.org/abs/1611.07995