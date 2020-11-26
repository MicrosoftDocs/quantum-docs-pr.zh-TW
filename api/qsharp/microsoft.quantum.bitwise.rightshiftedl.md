---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219510"
---
# <a name="rightshiftedl-function"></a>RightShiftedL 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將數位的位表示右移指定的位數。

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>輸入

### <a name="value--bigint"></a>值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要向右移動位標記法的數位， (較不重要的) 。


### <a name="amount--int"></a>數量： [Int](xref:microsoft.quantum.lang-ref.int)

要 `value` 向右移動的位數。



## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

的值 `value` ，以位向右移位 `amount` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```