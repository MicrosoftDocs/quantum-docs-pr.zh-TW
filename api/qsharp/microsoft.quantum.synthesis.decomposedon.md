---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203224"
---
# <a name="decomposedon-function"></a>DecomposedOn 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


分解變數上的排列

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>描述

指定排列 $ \pi $ (`perm`) 和索引 $i $ (`index`) ，這個方法會傳回三個排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，讓 $ \ pi_l $ 和 $ \ pi_r $ 的影像不會變更其元素中 $i $ 和 $ \pi ' $ 的影像中的位，而不會變更其專案中的位 $i $。

## <a name="input"></a>輸入

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) 

