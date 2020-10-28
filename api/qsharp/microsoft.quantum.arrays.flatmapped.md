---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699485"
---
# <a name="flatmapped-function"></a>FlatMapped 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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