---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843714"
---
# <a name="applyoutercdkmadder-operation"></a>ApplyOuterCDKMAdder 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


可回復的就地 ripple，包含在下面的整數加法運算 RippleCarryAdderCDKM 中使用的作業。
假設有兩個量子位暫存器 `xs` 和 `ys` 相同的長度，則作業會將 ripple 套用至 CNOT 和 CCNOT 閘道的順序，並以中的量子位作為 `xs` `ys` 控制項和量子位 `xs` 做為目標。

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第一個量子位註冊，包含控制項和目標。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第二個量子位註冊，參與控制項。


### <a name="ancilla--qubit"></a>ancilla： [量子位](xref:microsoft.quantum.lang-ref.qubit)

在 RippleCarryAdderCDKM 中使用的 ancilla 量子位會傳遞至這項作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考資料

- Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。
  https://arxiv.org/abs/quant-ph/0410184v1