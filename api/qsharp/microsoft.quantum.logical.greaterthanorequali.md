---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700574"
---
# <a name="greaterthanorequali-function"></a>GreaterThanOrEqualI 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有當數位大於或等於另一個數位時，才會傳回 true。

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要比較的第一個值。


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果 `a` 大於或等於，則為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```