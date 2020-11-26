---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221703"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回陣列中的順序元素需要交換以產生已排序的陣列。
假設進行交換。

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>輸入

### <a name="neworder--int"></a>newOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]

陣列，其中包含新陣列的索引排列。 應該有 $n $ 元素，每一個都是從 $0 $ 到 $n-$1 的唯一整數。



## <a name="output--intint"></a>輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元組代表要交換的兩個索引。 交換會從最小的索引開始。

## <a name="remarks"></a>備註

## <a name="psuedocode"></a>Psuedocode

針對 (index in 0.. Length (newOrder) -1) {while newOrder [index]！ = index {Switch newOrder [index] with newOrder [newOrder [index]]}}