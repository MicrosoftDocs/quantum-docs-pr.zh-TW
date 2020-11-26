---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211775"
---
# <a name="inferredlabel-function"></a>InferredLabel 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


由於分類機率和偏差的考慮，會傳回從該機率推斷的標籤。

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>輸入

### <a name="bias--double"></a>偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

兩個類別之間的偏差，通常是將分類器定型的結果。


### <a name="probability--double"></a>機率： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

特定範例的分類機率，通常是因為估計其分類頻率所產生。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

從指定分類機率推斷的標籤。