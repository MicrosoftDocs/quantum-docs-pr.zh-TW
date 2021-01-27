---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分割函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845548"
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



## <a name="example"></a>範例

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```