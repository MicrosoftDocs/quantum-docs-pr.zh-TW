---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854602"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum 函式

命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用黃金間隔搜尋，傳回單變數函式在限定間隔上的最小值。

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>輸入

### <a name="fn--double---double"></a>fn： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)

要最小化的單變數函數。


### <a name="bounds--doubledouble"></a>界限： ([雙精度](xref:microsoft.quantum.lang-ref.double)浮[點數](xref:microsoft.quantum.lang-ref.double)) 

要尋找區域最小值的間隔。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

函數輸入中要容許的精確度。
搜尋本機 optima 將會繼續進行，直到間隔小於此容錯的寬度為止。



## <a name="output--univariateoptimizationresult"></a>輸出： [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

指定之函式的本機 optima，位於指定的範圍內。