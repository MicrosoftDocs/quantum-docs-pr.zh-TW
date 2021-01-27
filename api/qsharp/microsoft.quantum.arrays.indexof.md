---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848517"
---
# <a name="indexof-function"></a>IndexOf 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列中第一個符合指定之述詞的第一個元素索引。 如果沒有這類元素，則傳回-1。

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>輸入

### <a name="predicate--t---bool"></a>述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)

在陣列元素上作用的述詞函式。


### <a name="arr--t"></a>arr： t []

要使用指定述詞搜尋的陣列。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

最小的索引 `idx` （例如 `predicate(arr[idx])` true），如果沒有這類元素，則為-1。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="example"></a>範例

假設這 `IsEven : Int -> Bool` 是一個函式， `true` 只有在其輸入為偶數時才會傳回。 然後，您可以搭配使用， `IndexOf` 以找出陣列中的第一個偶數元素：

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```