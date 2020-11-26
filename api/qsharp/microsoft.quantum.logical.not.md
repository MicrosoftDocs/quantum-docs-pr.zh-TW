---
uid: Microsoft.Quantum.Logical.Not
title: Not 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197444"
---
# <a name="not-function"></a>Not 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回值的布林值否定。

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>輸入

### <a name="value--bool"></a>值： [Bool](xref:microsoft.quantum.lang-ref.bool)

要反轉的值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果為，則為，如果為，則 `value` 為 `false` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let x = not value;
let x = Not(value);
```