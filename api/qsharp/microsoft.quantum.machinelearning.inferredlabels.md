---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700283"
---
# <a name="inferredlabels-function"></a>InferredLabels 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


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