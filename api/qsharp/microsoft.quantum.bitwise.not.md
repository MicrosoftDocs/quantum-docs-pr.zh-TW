---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842106"
---
# <a name="not-function"></a>Not 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回整數的位 NOT。
這會執行與內建運算子相同的計算 `~~~` 。

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>範例

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a>備註

如需詳細資訊，請參閱 [c # ~ 運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 。