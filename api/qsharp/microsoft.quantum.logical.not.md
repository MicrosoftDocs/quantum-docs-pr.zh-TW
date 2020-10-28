---
uid: Microsoft.Quantum.Logical.Not
title: Not 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697263"
---
# <a name="not-function"></a>Not 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


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