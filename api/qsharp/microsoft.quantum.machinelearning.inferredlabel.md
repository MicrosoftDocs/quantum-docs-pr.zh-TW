---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848410"
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