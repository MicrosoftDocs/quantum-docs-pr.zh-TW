---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848632"
---
# <a name="flatmapped-function"></a>FlatMapped 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設陣列和函式會將陣列元素對應至某些輸出陣列，則會傳回每個陣列元素的串連輸出陣列。

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>輸入

### <a name="mapper--tinput---toutput"></a>對應工具： ' TInput-> ' Toutput> []

中 `'TInput` `'TOutput[]` 用來對應陣列元素的函式。


### <a name="array--tinput"></a>陣列： ' TInput []

元素的陣列。



## <a name="output--toutput"></a>輸出： ' Toutput> []

的陣列， `'TOutput[]` 這是對應函式所產生之所有陣列的串連。

## <a name="type-parameters"></a>類型參數

### <a name="tinput"></a>'TInput

元素的類型 `array` 。
### <a name="toutput"></a>' Toutput>

函數會傳回 `mapper` 這個類型的陣列。

## <a name="example"></a>範例

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```