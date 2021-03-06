---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846499"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在量子位暫存器上以整數常數執行模組化乘法。

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

讓我們 `modulus` 以 $N $ 和 `constMultiplier` by $a $ 表示。
然後，這項作業會根據計算基礎來執行下列對應所定義的單一作業： $ $ \begin{align} \ket{y} \mapsto \ket{ (\cdot y) \operatorname{mod} N} \end{align} $ $，適用于 $0 $ 和 $N-$1 之間的所有 $y $。

## <a name="input"></a>輸入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

乘以乘數的常數。 必須是與模數的共同質數。


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

乘法運算會執行模數 `modulus` 。


### <a name="multiplier--littleendian"></a>乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要乘以常數的數位。
這是以位元組由小到大格式的整數量子位編碼的陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

- 如需電路圖和說明，請參閱[arXiv： quant-ph/0205095V3 頁面 8](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)上的圖7。
- 此作業對應到[arXiv： quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)中的 u ₐ