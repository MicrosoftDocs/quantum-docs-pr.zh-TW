---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699382"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

包： [](https://nuget.org/packages/)


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