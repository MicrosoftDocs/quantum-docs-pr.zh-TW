---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194826"
---
# <a name="plusa-function"></a>PlusA 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回兩個輸入 (串連) 的總和。

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>輸入

### <a name="a--element"></a>a： ' Element []

要加總的第一個輸入 $a $。


### <a name="b--element"></a>b： ' Element []

第二個輸入 $b $ 以加總。



## <a name="output--element"></a>Output： ' Element []

Sum $a + b $。

## <a name="type-parameters"></a>類型參數

### <a name="element"></a>' 元素

這兩個輸入陣列中每個元素的型別。