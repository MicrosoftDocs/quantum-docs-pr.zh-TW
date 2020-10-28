---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700810"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult 使用者定義型別

命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)

包： [](https://nuget.org/packages/)


表示優化單變數函數的結果。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>命名專案

### <a name="coordinate--double"></a>座標： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

找到最佳的輸入。
### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

函數所傳回的最理想值。