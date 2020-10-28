---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698226"
---
# <a name="rangereverse-function"></a>RangeReverse 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

包： [](https://nuget.org/packages/)


傳回新的範圍，這是輸入範圍的反向。

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>輸入

### <a name="r--range"></a>r： [範圍](xref:microsoft.quantum.lang-ref.range)

輸入範圍。



## <a name="output--range"></a>輸出： [範圍](xref:microsoft.quantum.lang-ref.range)

指定範圍反轉的新範圍。

## <a name="remarks"></a>備註

請注意，範圍的反向不只是 `end` ... `-step` `start` ，因為範圍的實際最後一個元素可能不 `end` 會與相同。