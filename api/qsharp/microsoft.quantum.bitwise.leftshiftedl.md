---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219663"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將數位的位表示向左移位指定的位數。

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>輸入

### <a name="value--bigint"></a>值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要向左移動位標記法的數位， (更重要的) 。


### <a name="amount--int"></a>數量： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移位的位數 `value` 。



## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

的值 `value` ，以位向左移位 `amount` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```