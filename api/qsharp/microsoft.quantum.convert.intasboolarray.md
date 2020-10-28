---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698290"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

包： [](https://nuget.org/packages/)


針對傳回的陣列，使用位元組由小到大的標記法，產生正整數的整數表示。

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>輸入

### <a name="number--int"></a>數位： [Int](xref:microsoft.quantum.lang-ref.int)

要轉換成布林值陣列的正整數。


### <a name="bits--int"></a>位： [Int](xref:microsoft.quantum.lang-ref.int)

二進位表示中的位數目 `number` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

表示的布林值陣列 `number` 。

## <a name="remarks"></a>備註

輸入 `bits` 必須介於0到63之間。
輸入 `number` 必須介於0到 $ 2 ^ {\texttt{bits}}-$1 之間。