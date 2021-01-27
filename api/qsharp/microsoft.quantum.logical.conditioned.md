---
uid: Microsoft.Quantum.Logical.Conditioned
title: 條件式函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817291"
---
# <a name="conditioned-function"></a>條件式函數

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```