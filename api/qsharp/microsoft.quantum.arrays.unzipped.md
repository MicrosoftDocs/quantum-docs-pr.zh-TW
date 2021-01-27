---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解壓縮的函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845374"
---
# <a name="unzipped-function"></a>解壓縮的函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有2個元組的陣列，會傳回兩個數組的元組，每個陣列都包含輸入陣列的元組的元素。

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>輸入

### <a name="arr--tu"></a>arr： ( t，' U) []

包含2個元組的陣列



## <a name="output--tu"></a>Output： ( t []，' U [] ) 

兩個數組，第一個是包含輸入元組的所有第一個專案，第二個是包含輸入元組的所有第二個元素。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個元組中第一個元素的類型
### <a name="u"></a>' U

每個元組中第二個元素的類型

## <a name="example"></a>範例

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>另請參閱

- [Microsoft.Quantum.Arrays.Ziped](xref:Microsoft.Quantum.Arrays.Zipped)