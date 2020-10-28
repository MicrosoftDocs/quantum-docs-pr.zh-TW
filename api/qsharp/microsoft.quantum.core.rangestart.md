---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698207"
---
# <a name="rangestart-function"></a>RangeStart 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

包： [](https://nuget.org/packages/)


傳回指定範圍的已定義開始值。

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>輸入

### <a name="range--range"></a>範圍： [範圍](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

指定範圍的已定義開始值。

## <a name="remarks"></a>備註

範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。

請注意，範圍的定義開始值與序列的第一個元素相同，除非範圍指定空的序列 (例如，2。 1)。