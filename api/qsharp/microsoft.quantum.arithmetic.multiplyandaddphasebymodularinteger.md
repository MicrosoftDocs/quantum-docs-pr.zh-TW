---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843068"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


與 MultiplyAndAddByModularInteger 相同，但假設被加數會以 QFT 為基礎來編碼整數。

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

要加入至每個基礎狀態標籤的 $a $ 的整數。


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

模數 $N $ 所採用的加法和乘法。


### <a name="multiplier--littleendian"></a>乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

代表不帶正負號整數的量子暫存器，其值要加入至的每個基礎狀態標籤 `summand` 。


### <a name="phasesummand--phaselittleendian"></a>phaseSummand： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

量子暫存器，代表要作為此作業目標的不帶正負號的整數。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

假設 `phaseSummand` 最大位設定為0。
也假設的值 `phaseSummand` 小於 $N $。

## <a name="see-also"></a>另請參閱

- [MultiplyAndAddByModularInteger。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)