---
uid: Microsoft.Quantum.Logical.Or
title: Or 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197121"
---
# <a name="or-function"></a>Or 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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