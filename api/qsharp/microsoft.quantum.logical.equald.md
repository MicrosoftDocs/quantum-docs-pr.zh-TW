---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816875"
---
# <a name="equald-function"></a>EqualD 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


只有當兩個輸入相等時，才會傳回 true。

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="a--double"></a>a： [Double](xref:microsoft.quantum.lang-ref.double)

要比較的第一個值。


### <a name="b--double"></a>b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有當 `a` 等於時，才為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```