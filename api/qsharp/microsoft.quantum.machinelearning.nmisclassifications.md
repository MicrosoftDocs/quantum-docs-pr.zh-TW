---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697227"
---
# <a name="nmisclassifications-function"></a>NMisclassifications 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引數目。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>輸入

### <a name="proposed--int"></a>提議： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>實際： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

索引的數目 `idx` `inferredLabels[idx] != actualLabels[idx]` 。