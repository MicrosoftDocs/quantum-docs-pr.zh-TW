---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699927"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


RippleCarryAdderCDKM 中的核心作業，用於上述 ApplyOuterCDKMAdder 作業，也就是 conjugated 與此作業，以取得 RippleCarryAdderCDKM 的內部作業。 這項作業會計算執行量子位，並在輸入的部分套用非閘道序列 `ys` 。

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第一個量子位報名。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第二個量子位註冊。


### <a name="ancilla--qubit"></a>ancilla： [量子位](xref:microsoft.quantum.lang-ref.qubit)

在 RippleCarryAdderCDKM 中使用的 ancilla 量子位會傳遞至這項作業。


### <a name="carry--qubit"></a>攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)

在 RippleCarryAdderCDKM 作業中執行量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。
  https://arxiv.org/abs/quant-ph/0410184v1