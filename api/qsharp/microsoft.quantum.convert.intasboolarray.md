---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833310"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對傳回的陣列，使用位元組由小到大的標記法，針對非負整數產生二進位標記法。

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>輸入

### <a name="number--int"></a>數位： [Int](xref:microsoft.quantum.lang-ref.int)

要轉換成布林值陣列的非負整數。


### <a name="bits--int"></a>位： [Int](xref:microsoft.quantum.lang-ref.int)

二進位表示中的位數目 `number` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

表示的布林值陣列 `number` 。

## <a name="remarks"></a>備註

輸入 `bits` 必須介於0到63之間。
輸入 `number` 必須介於0到 $ 2 ^ {\texttt{bits}}-$1 之間。