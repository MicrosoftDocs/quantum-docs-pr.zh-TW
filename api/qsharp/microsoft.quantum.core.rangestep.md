---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853606"
---
# <a name="rangestep-function"></a>RangeStep 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回整數，這個整數會指定如何計算範圍的下一個值。

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>輸入

### <a name="range--range"></a>範圍： [範圍](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

指定範圍的已定義步驟值。

## <a name="remarks"></a>備註

範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。