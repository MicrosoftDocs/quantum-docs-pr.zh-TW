---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699461"
---
# <a name="ispermutation-function"></a>IsPermutation 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


只有當指定的陣列表示排列時，才會輸出 true。

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>描述

指定長度的陣列時 `array` `n` ，如果和只有在中的每個整數只出現一次，就會傳回 true， `0` 這樣就 `n - 1` `array` `array` 可以將它視為元素上的相片順序 `n` 。

## <a name="input"></a>輸入

### <a name="permuation--int"></a>permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]

不一定代表排列的陣列。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>備註

長度為零的陣列會完整排列。