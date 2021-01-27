---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846591"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以整數常數執行量子位暫存器的模組化增量。

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

讓我們以 `increment` $a $）來表示， `modulus` $N $ 和以 $y $ 編碼的整數 `target` 。
然後，作業會執行下列轉換： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整數以位元組由小到大的格式編碼。

## <a name="input"></a>輸入

### <a name="increment--int"></a>遞增： [Int](xref:microsoft.quantum.lang-ref.int)

要加入 $y $ 的整數遞增 $a $。


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

Mods > $y + a $ 的整數 $N $。


### <a name="target--littleendian"></a>目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`LittleEndian`$A $ 新增至的格式的整數 $y $ `increment` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

假設目標的起始值小於 $N $，而遞增 $a $ 小於 $N $。
請注意，會 <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 在基礎中執行相同的作業 `PhaseLittleEndian` 。

## <a name="see-also"></a>另請參閱

- [IncrementPhaseByModularInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)