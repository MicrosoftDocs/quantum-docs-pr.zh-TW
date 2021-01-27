---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848669"
---
# <a name="exclude-function"></a>Exclude 函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列，其中包含另一個陣列的元素，但不包括指定之索引清單中的元素。

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="remove--int"></a>remove： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列，表示應從輸出中排除的元素。


### <a name="array--t"></a>陣列： t []

輸出陣列中的值所採用的陣列。



## <a name="output--t"></a>Output： t []

陣列 `output` `output[0]` ，這是 `array` 其索引不會出現在中的第一個專案 `remove` ，例如 `output[1]` 第二個這類元素等等。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列元素的類型。

## <a name="example"></a>範例

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```