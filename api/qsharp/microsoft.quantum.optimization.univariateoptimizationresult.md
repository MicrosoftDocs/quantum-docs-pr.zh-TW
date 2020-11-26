---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194027"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult 使用者定義型別

命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示優化單變數函數的結果。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>命名專案

### <a name="coordinate--double"></a>座標： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

找到最佳的輸入。
### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

函數所傳回的最理想值。