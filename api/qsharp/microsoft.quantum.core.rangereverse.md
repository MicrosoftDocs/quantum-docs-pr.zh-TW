---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213832"
---
# <a name="rangereverse-function"></a>RangeReverse 函式

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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