---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855410"
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

## <a name="example"></a>範例

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```