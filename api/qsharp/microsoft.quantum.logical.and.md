---
uid: Microsoft.Quantum.Logical.And
title: And 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699759"
---
# <a name="and-function"></a>And 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


傳回兩個值的布林值結合。

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>輸入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第一個值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果和 `a` `b` 都是，則為 `true` 。

## <a name="remarks"></a>備註

與運算子不同的 `and` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。

最高的最小運算行為，如下所示：

```Q#
let x = a and b;
let x = And(a, b);
```