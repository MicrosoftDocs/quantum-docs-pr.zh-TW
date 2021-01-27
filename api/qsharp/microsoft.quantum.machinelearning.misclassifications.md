---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 情形函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853934"
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

## <a name="example"></a>範例

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```