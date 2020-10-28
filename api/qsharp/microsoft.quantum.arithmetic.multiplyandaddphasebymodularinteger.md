---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699577"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


與 MultiplyAndAddByModularInteger 相同，但假設被加數會以 QFT 為基礎來編碼整數。

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
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