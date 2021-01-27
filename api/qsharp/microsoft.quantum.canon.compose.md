---
uid: Microsoft.Quantum.Canon.Compose
title: 撰寫函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840913"
---
# <a name="compose-function"></a>撰寫函數

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回兩個函數的組合。

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>描述

假設有兩個函數 $f $ 和 $g $，則會傳回代表 $f \circ g $ 的新函式。

## <a name="input"></a>輸入

### <a name="outer--u---v"></a>外部： ' U-> ' V

要套用的第二個函數。


### <a name="inner--t---u"></a>內部： t-> ' U

要套用的第一個函數。



## <a name="output--t---v"></a>輸出： t-> ' V

新的函式 $h $，用於所有輸入 $x $、$f (g (x) # A3 = h (x) $。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之第一個函數的輸入類型。
### <a name="u"></a>' U

要套用之第一個函式的輸出類型，以及要套用之第二個函式的輸入類型。
### <a name="v"></a>' V

要套用之第二個函數的輸出類型。