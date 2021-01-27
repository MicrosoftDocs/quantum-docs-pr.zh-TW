---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840080"
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