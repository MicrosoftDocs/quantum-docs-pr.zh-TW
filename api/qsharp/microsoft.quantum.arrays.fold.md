---
uid: Microsoft.Quantum.Arrays.Fold
title: 折迭函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221159"
---
# <a name="fold-function"></a>折迭函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


`f`透過陣列逐一查看函式 `array` ，傳回 `f(f(f(initialState, array[0]), array[1]), ...)` 。

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>輸入

### <a name="folder--statet---state"></a>資料夾： ( ' 狀態，不) -> ' 狀態

要在陣列上折迭的函式。


### <a name="state--state"></a>狀態： ' State

資料夾的初始狀態。


### <a name="array--t"></a>陣列： t []

要折迭的值陣列。



## <a name="output--state"></a>輸出： ' 狀態

在逐一查看的所有專案之後，資料夾所傳回的最終狀態 `array` 。

## <a name="type-parameters"></a>類型參數

### <a name="state"></a>' 狀態

函式運作的狀態類型 `folder` ，也就是接受作為其第一個引數並傳回。
### <a name="t"></a>不要

元素的類型 `array` 。