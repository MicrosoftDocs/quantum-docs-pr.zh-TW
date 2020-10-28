---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699578"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>MultiplyAndAddByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


在量子位暫存器上，以整數常數執行模組化乘法和 add。

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

針對指定的模數，將 map $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{ (b + a \cdot x) \operatorname{mod} N} \end{align} $ $ $N $、常數乘數 $a $ 和被加數 $y $。

## <a name="input"></a>輸入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

要加入至每個基礎狀態標籤的 $a $ 的整數。


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

模數 $N $ 所採用的加法和乘法。


### <a name="multiplier--littleendian"></a>乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

代表不帶正負號整數的量子暫存器，其值要加入至的每個基礎狀態標籤 `summand` 。


### <a name="summand--littleendian"></a>被加數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

量子暫存器，代表要作為此作業目標的不帶正負號的整數。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

- 如需電路圖和說明，請參閱[arXiv： quant-ph/0205095V3 頁面 7](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)上的圖6
- 此作業對應于 CMULT () MOD (N) 在 [arXiv： quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>另請參閱

- [MultiplyAndAddPhaseByModularInteger。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)