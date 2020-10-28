---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699373"
---
# <a name="rightshiftedi-function"></a>RightShiftedI 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

包： [](https://nuget.org/packages/)


將數位的位表示右移指定的位數。

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

要向右移動位標記法的數位， (較不重要的) 。


### <a name="amount--int"></a>數量： [Int](xref:microsoft.quantum.lang-ref.int)

要 `value` 向右移動的位數。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

的值 `value` ，以位向右移位 `amount` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```