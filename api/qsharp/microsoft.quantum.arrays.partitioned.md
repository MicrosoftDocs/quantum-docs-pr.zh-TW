---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分割函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220496"
---
# <a name="partitioned-function"></a>分割函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將陣列分割成多個部分。

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>輸入

### <a name="nelements--int"></a>nElements： [Int](xref:microsoft.quantum.lang-ref.int)[]

陣列中每個部分的元素數目


### <a name="arr--t"></a>arr： t []

要分割的輸入陣列。



## <a name="output--t"></a>Output： t [] []

多個陣列，其中第一個陣列是第一個陣列 `nElements[0]` `arr` ，而第二個數組是下一個陣列 `nElements[1]` `arr` 。最後一個陣列將包含所有剩餘的元素。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

