---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699851"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


使用階段旋轉，以傳統整數遞增未簽署的量子暫存器。

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a>描述

假設將 `target` 不帶正負號的整數編碼 $x $ 以位元組由小到大的編碼方式，且 `increment` 等於 $a $。
然後，這項作業會執行單一 $ \ket{x} \mapsto \ket{x + a} $，其中加法會執行模數 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。

## <a name="input"></a>輸入

### <a name="increment--int"></a>遞增： [Int](xref:microsoft.quantum.lang-ref.int)

用來遞增的整數 `target` 。


### <a name="target--phaselittleendian"></a>目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

量子暫存器會以雙重 (QFT) 基礎，使用位元組由大到小的編碼方式來編碼不帶正負號的整數。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

請注意，我們已簡化電路，因為遞增是傳統的常數，而不是量子暫存器。

請參閱 [ arXiv： quant-ph/0008033v1 的第6頁 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) 中的圖表，以取得路線圖和說明。

## <a name="references"></a>參考

- [*Thomas G. Draper* 、arXiv： quant-ph/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>另請參閱

- [IncrementByInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)