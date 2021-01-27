---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848400"
---
# <a name="inferredlabels-function"></a>InferredLabels 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


由於分類機率和偏差的陣列，會傳回從每個機率推斷的標籤。

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>輸入

### <a name="bias--double"></a>偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

兩個類別之間的偏差，通常是將分類器定型的結果。


### <a name="probabilities--double"></a>機率： [Double](xref:microsoft.quantum.lang-ref.double)[]

一組範例的分類機率陣列，通常是因為估計分類頻率所產生。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

從每個分類機率推斷的標籤。