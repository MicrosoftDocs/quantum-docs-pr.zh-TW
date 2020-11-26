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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="d2feb-102">UnivariateOptimizationResult 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d2feb-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="d2feb-103">命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="d2feb-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="d2feb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2feb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2feb-105">表示優化單變數函數的結果。</span><span class="sxs-lookup"><span data-stu-id="d2feb-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="d2feb-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="d2feb-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="d2feb-107">座標： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2feb-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2feb-108">找到最佳的輸入。</span><span class="sxs-lookup"><span data-stu-id="d2feb-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="d2feb-109">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2feb-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2feb-110">函數所傳回的最理想值。</span><span class="sxs-lookup"><span data-stu-id="d2feb-110">Value returned by the function at its optimum.</span></span>