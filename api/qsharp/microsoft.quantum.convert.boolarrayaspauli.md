---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698331"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

包： [](https://nuget.org/packages/)


指定一個位字串，會傳回多量子位的 Pauli 運算子，以單一量子位 Pauli 運算子的陣列表示。

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 運算子，適用于量子位 where `bitsApply == bits[idx]` 。


### <a name="bitapply--bool"></a>bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果位為此值，則套用 Pauli。


### <a name="bits--bool"></a>位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

布林陣列。



## <a name="output--pauli"></a>輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>備註

布林陣列和量子暫存器的長度必須相等。