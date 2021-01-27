---
uid: Microsoft.Quantum.Arrays.Chunks
title: 區塊函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842882"
---
# <a name="chunks-function"></a>區塊函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將陣列分割為相等長度的多個部分。

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>輸入

### <a name="nelements--int"></a>nElements： [Int](xref:microsoft.quantum.lang-ref.int)

每個區塊的長度。


### <a name="arr--t"></a>arr： t []

要分割的陣列。



## <a name="output--t"></a>Output： t [] []

陣列，其中包含原始陣列的每個區塊。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

請注意，輸出的最後一個元素可能會比無法整除的還短 `nElements` `Length(arr)` `nElements` 。