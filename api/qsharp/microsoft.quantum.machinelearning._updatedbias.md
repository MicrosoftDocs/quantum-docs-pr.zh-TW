---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 41a51d8a6a8af299ce3e84b727336b098a3d1160
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844435"
---
# <a name="_updatedbias-function"></a>_UpdatedBias 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回會導致接近最小分類誤判分數的偏差值。

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>輸入

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities： ([Double](xref:microsoft.quantum.lang-ref.double)，[Int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

