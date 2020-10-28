---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699846"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


以整數常數執行量子位暫存器的模組化增量。

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a>描述

讓我們以 `increment` $a $）來表示， `modulus` $N $ 和以 $y $ 編碼的整數 `target` 。
然後，此作業會執行下列轉換： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整數以為基礎的位元組由大到小的格式進行編碼。

## <a name="input"></a>輸入

### <a name="increment--int"></a>遞增： [Int](xref:microsoft.quantum.lang-ref.int)

要加入 $y $ 的整數遞增 $a $。


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

Mods > $y + a $ 的整數 $N $。


### <a name="target--phaselittleendian"></a>目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

整數 $y $ in 階段編碼的位元組由大到小的格式， `increment` $a $ 新增至。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

假設 `target` 最大位設定為0。
也假設目標的值小於 $N $。

如需電路圖和說明，請參閱 [arXiv： quant-ph/0205095V3 第5頁](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)上的圖5。

## <a name="see-also"></a>另請參閱

- [IncrementByModularInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)