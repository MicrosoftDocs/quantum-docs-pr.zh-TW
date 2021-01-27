---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845315"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將數位的位表示向左移位指定的位數。

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移動位標記法的數位， (更重要的) 。


### <a name="amount--int"></a>數量： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移位的位數 `value` 。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

的值 `value` ，以位向左移位 `amount` 。

## <a name="remarks"></a>備註

以下是相等的：

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```