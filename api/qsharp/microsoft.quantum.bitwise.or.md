---
uid: Microsoft.Quantum.Bitwise.Or
title: Or 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845272"
---
# <a name="or-function"></a>Or 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回兩個整數的位 OR。
這會執行與內建運算子相同的計算 `|||` 。

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>範例

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a>備註

請參閱 [c # |運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) 以取得詳細資料。