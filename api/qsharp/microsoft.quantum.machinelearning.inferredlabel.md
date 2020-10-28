---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700294"
---
# <a name="inferredlabel-function"></a>InferredLabel 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


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