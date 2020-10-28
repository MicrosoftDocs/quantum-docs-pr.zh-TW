---
uid: Microsoft.Quantum.Logical.Or
title: Or 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699606"
---
# <a name="or-function"></a>Or 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


傳回兩個值的布林分離。

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>輸入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第一個值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果或為，則 `a` 為，否則 `b` 為 `true` 。

## <a name="remarks"></a>備註

與運算子不同的 `or` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。

最高的最小運算行為，如下所示：

```Q#
let x = a or b;
let x = Or(a, b);
```