---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219850"
---
# <a name="zip-function"></a>Zip 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip 已淘汰。 請改用 <xref:Microsoft.Quantum.Arrays.Zipped>。

假設有兩個數組，會傳回一組新的陣列，讓每一組都包含每個原始陣列中的元素。

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>輸入

### <a name="left--t"></a>左方： t []

陣列，其中包含每個元組的第一個元素值。


### <a name="right--u"></a>right： ' U []

陣列，其中包含每個元組的第二個元素的值。



## <a name="output--tu"></a>Output： ( t，' U) []

陣列，其中包含每個的表單配對 `(left[idx], right[idx])` `idx` 。 如果兩個數組的長度不相等，則輸出將會是輸入較短的時間長度。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

左方陣列元素的型別。
### <a name="u"></a>' U

右陣列元素的型別。

## <a name="see-also"></a>另請參閱

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [。已解壓縮](xref:Microsoft.Quantum.Arrays.Unzipped)