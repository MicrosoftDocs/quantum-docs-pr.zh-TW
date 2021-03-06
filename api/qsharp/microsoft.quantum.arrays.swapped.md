---
uid: Microsoft.Quantum.Arrays.Swapped
title: 交換函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850957"
---
# <a name="swapped-function"></a>交換函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對陣列中的兩個元素套用交換。

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>輸入

### <a name="firstindex--int"></a>firstIndex： [Int](xref:microsoft.quantum.lang-ref.int)

要交換之第一個元素的索引。


### <a name="secondindex--int"></a>secondIndex： [Int](xref:microsoft.quantum.lang-ref.int)

要交換的第二個元素的索引。


### <a name="arr--t"></a>arr： t []

具有要交換之元素的陣列。



## <a name="output--t"></a>Output： t []

套用了就地交換的陣列。

## <a name="example"></a>範例

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

