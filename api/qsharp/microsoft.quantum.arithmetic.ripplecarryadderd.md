---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699541"
---
# <a name="ripplecarryadderd-operation"></a>RippleCarryAdderD 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


可還原的就地 ripple-包含兩個整數的加法。
假設有兩個 $n $ bit 整數編碼在 LittleEndian 暫存器中 `xs` `ys` ，而且量子位包含，則作業會計算兩個整數的總和，其中會保留結果的 $n $ 最低有效位數 `ys` ，而執行時位會進行 xor 至量子位 `carry` 。

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位登錄第一個整數被加數的編碼。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位暫存器第二個整數被加數的編碼，會修改成保存總和的 $n $ 最不重要的位。


### <a name="carry--qubit"></a>攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)

帶有量子位，是以總和的最高有效位進行 xor。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。

## <a name="references"></a>參考

- Thomas g. Draper：「在量子電腦上新增」，2000。
  https://arxiv.org/abs/quant-ph/0008033