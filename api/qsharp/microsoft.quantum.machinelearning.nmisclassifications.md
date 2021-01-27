---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853908"
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

## <a name="example"></a>範例

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```