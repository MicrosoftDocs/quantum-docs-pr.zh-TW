---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831106"
---
# <a name="rangestart-function"></a>RangeStart 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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