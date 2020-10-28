---
uid: Microsoft.Quantum.Arrays.Merged
title: 合併函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699445"
---
# <a name="merged-function"></a>合併函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


假設有兩個已排序的陣列，會傳回單一陣列，其中包含兩個專案的排序次序。 由定序排列在內部使用。

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="comparison--tt---bool"></a>比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>左方： t []




### <a name="right--t"></a>right： t []





## <a name="output--t"></a>Output： t []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

