---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845264"
---
# <a name="rightshiftedi-function"></a>RightShiftedI 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```