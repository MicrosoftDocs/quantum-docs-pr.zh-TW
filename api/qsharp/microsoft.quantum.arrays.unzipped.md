---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解壓縮的函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699408"
---
# <a name="unzipped-function"></a>解壓縮的函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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

## <a name="see-also"></a>另請參閱

- [Microsoft.Quantum.Arrays.Ziped](xref:Microsoft.Quantum.Arrays.Zipped)