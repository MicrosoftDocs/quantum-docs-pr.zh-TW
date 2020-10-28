---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700515"
---
# <a name="xor-function"></a>Xor 函數

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


傳回兩個值的布林專屬分隔分離。

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>輸入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第一個值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考慮的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有當和都只有一個時，才 `a` `b` 會 `true` 。