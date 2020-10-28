---
uid: Microsoft.Quantum.Logical.Conditioned
title: 條件式函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699755"
---
# <a name="conditioned-function"></a>條件式函數

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


根據布林值條件的值，傳回兩個值的其中一個。

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>輸入

### <a name="condition--bool"></a>條件： [Bool](xref:microsoft.quantum.lang-ref.bool)

用來控制傳回之輸入的條件。


### <a name="iftrue--t"></a>ifTrue： t

當為時要傳回的 `condition` 值 `true` 。


### <a name="iffalse--t"></a>ifFalse： t

當為時要傳回的 `condition` 值 `false` 。



## <a name="output--t"></a>輸出： t

`ifTrue` 如果 `condition` 為 `true` ，則為， `ifFalse` 否則為。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

與運算子不同的 `?|` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。

最高的最小運算行為，如下所示：

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```