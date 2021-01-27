---
uid: Microsoft.Quantum.Core.RangeEnd
title: 到 rangeend 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831373"
---
# <a name="rangeend-function"></a>到 rangeend 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回指定範圍的定義結束值，這不一定是序列中的最後一個元素。

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>輸入

### <a name="range--range"></a>範圍： [範圍](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

指定範圍的定義結束值。

## <a name="remarks"></a>備註

範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。

請注意，定義的範圍結束值可能會與範圍所指定之序列中的最後一個元素不同;例如，在範圍0中。 2。 5最後一個元素是4，但結束值為5。