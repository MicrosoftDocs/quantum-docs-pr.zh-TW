---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697190"
---
# <a name="plusa-function"></a>PlusA 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


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