---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226072"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring 函式

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


的傳統處理步驟 `ApplyDeltaParity` 。
這會計算用來評估任何兩個 PQRS 之間的同位差異的控制項量子位清單 .。。偶數長度的詞彙。

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>輸入

### <a name="prevfermionicterm--int"></a>prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) 



## <a name="remarks"></a>備註

這假設詞彙的長度是偶數。
針對任何兩個詞彙之間的同位差異，計算控制項清單。
這會假設輸入清單是以遞增順序排序。