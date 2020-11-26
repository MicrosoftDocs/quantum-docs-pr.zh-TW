---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214274"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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