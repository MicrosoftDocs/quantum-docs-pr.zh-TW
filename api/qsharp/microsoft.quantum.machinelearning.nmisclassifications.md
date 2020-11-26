---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196305"
---
# <a name="nmisclassifications-function"></a>NMisclassifications 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


假設有一組推斷的標籤和一組正確的標籤，則會傳回每一組標籤不同的索引數目。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>輸入

### <a name="proposed--int"></a>提議： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>實際： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

索引的數目 `idx` `inferredLabels[idx] != actualLabels[idx]` 。