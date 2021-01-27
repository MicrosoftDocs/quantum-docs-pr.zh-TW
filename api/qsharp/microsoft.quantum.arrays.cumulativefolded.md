---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846234"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將對應和折迭合併為單一函式

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>描述

此函式 `fn` 會從初始狀態開始，透過陣列來逐一查看函式， `state` 並傳回所有的中繼值，而不包含初始狀態。

## <a name="input"></a>輸入

### <a name="fn--statet---state"></a>fn： ( ' State，t) -> ' 狀態

要在陣列上折迭的函式


### <a name="state--state"></a>狀態： ' State

要折迭的初始狀態


### <a name="array--t"></a>陣列： t []

要折迭的值陣列



## <a name="output--state"></a>輸出： ' State []

所有中繼狀態，包括最終狀態，但不包含初始狀態。
輸出陣列的長度與相同 `array` 。

## <a name="type-parameters"></a>類型參數

### <a name="state"></a>' 狀態

函式運作的狀態類型 `fn` ，也就是接受它的第一個輸入並傳回。
### <a name="t"></a>不要

元素的類型 `array` 。

## <a name="example"></a>範例

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```