---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231087"
---
# <a name="integerbits-function"></a>IntegerBits 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回設定整數位的所有位置。

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

非負數值。


### <a name="length--int"></a>長度： [Int](xref:microsoft.quantum.lang-ref.int)

的二進位擴充中的位數目 `value` 。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

包含所有位位置的陣列 (從0開始，在二元擴充中，會將 `value` 所有位視為最高的位置 1) `length - 1` 。  所有位置都會依位置以遞增順序排列在陣列中。