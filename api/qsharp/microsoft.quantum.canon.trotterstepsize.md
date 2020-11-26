---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204686"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


計算 Trotter 模擬演算法的遞迴實 Trotter 步驟大小。

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>輸入

### <a name="order--int"></a>order： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>備註

這項作業會使用與 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)不同的索引慣例。 尤其是，會 `DecomposedIntoTimeStepsCA(_, 4)` 對應到 quant-ph/0508139 中的純量 $p _2 ( \lambda) $。