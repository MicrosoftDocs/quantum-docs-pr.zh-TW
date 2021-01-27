---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854574"
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