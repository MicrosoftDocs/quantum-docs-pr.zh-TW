---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 情形函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211673"
---
# <a name="misclassifications-function"></a>情形函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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