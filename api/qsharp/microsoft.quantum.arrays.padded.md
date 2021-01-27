---
uid: Microsoft.Quantum.Arrays.Padded
title: 填補的函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845554"
---
# <a name="padded-function"></a>填補的函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回以指定的值填補的陣列（最多指定長度）。

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="nelementstotal--int"></a>nElementsTotal： [Int](xref:microsoft.quantum.lang-ref.int)

填補陣列的長度。 如果這是正面的， `inputArray` 則會在標頭填補。 如果是負數， `inputArray` 則會在結尾填補。


### <a name="defaultelement--t"></a>defaultElement： t

要用於填補元素的預設值。


### <a name="inputarray--t"></a>inputArray： t []

其值位於輸出陣列開頭的陣列。



## <a name="output--t"></a>Output： t []

陣列，該陣列 `output` 是 `inputArray` 以 s 為開頭且 `defaultElement` `output` 長度為的。 `nElementsTotal`

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。

## <a name="example"></a>範例

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```