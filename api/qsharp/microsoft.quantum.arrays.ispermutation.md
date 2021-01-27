---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848102"
---
# <a name="ispermutation-function"></a>IsPermutation 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>範例

下列 Q # 程式碼會列印「所有診斷已順利完成」訊息：

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>備註

長度為零的陣列會完整排列。