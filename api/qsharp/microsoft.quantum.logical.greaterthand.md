---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697303"
---
# <a name="greaterthand-function"></a>GreaterThanD 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

包： [](https://nuget.org/packages/)


只有當數位大於另一個數位時，才會傳回 true。

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="a--double"></a>a： [Double](xref:microsoft.quantum.lang-ref.double)

要比較的第一個值。


### <a name="b--double"></a>b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

要比較的第二個值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 只有在 `a` 完全大於時，才為 `b` 。

## <a name="remarks"></a>備註

以下是相等的：

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```