---
uid: Microsoft.Quantum.Arrays.ElementAt
title: Parameters.alternatefilters.elementat 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842810"
---
# <a name="elementat-function"></a>Parameters.alternatefilters.elementat 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回位於陣列中指定索引處的。

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a>輸入

### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)

元素的索引


### <a name="array--t"></a>陣列： t []

要編制索引的陣列。



## <a name="output--t"></a>輸出： t



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="example"></a>範例

取得四個知名整數序列中的第三個數字。  (請注意，0索引會對應到序列的 _第一個_ 值。 ) 

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a>另請參閱

- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [ElementsAt。](xref:Microsoft.Quantum.Arrays.ElementsAt)