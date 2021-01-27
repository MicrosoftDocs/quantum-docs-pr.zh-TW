---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814512"
---
# <a name="notequali-function"></a>NotEqualI 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


只有在兩個輸入不相等時，才會傳回 true。

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要比較的第一個值。


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 如果和 `a` 不等於，則為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```