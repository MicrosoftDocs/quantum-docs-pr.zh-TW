---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 情形函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700598"
---
# <a name="misclassifications-function"></a>情形函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引。

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>輸入

### <a name="inferredlabels--int"></a>inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]

針對指定定型或驗證集所推斷的標籤。


### <a name="actuallabels--int"></a>actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]

給定定型或驗證集的真實標籤。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。