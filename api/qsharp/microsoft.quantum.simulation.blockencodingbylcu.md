---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700963"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將感興趣的運算子編碼為 `BlockEncoding` 。

這會建立 `BlockEncoding` 單一 $U = P\cdot V\cdot P ^ \dagger $，以將某些運算子編碼 $H = \ sum_ {j} | \ Alpha_j |Unitaries 的線性組合 U_j $。 一般來說，$P $ 是單一狀態準備，因此 $P \ket {0} \_ a = \ sum_j \sqrt{\ Alpha_j/ \| \vec\Alpha \| \_ 2} \ket{j} \_ a $ 和 $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

單一的 $P $，可準備某個目標狀態。


### <a name="selector--ts--unit-adj--ctl"></a>選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

將 $H $ 的元件 unitaries 編碼的單一 $V $。



## <a name="output--ts--unit-adj--ctl"></a>輸出： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

單一的 $U $ 可共同處理暫存器 `a` 和 `s` 區塊編碼 $H $，並且滿足 $U ^ \Dagger = U $。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="s"></a>者



## <a name="remarks"></a>備註

這 `BlockEncoding` 項執行會提供它的屬性 `BlockEncodingReflection` 。

## <a name="see-also"></a>另請參閱

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)