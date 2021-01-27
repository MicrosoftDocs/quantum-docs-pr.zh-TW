---
uid: Microsoft.Quantum.Arrays.Fold
title: 折迭函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848613"
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

## <a name="example"></a>範例

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```