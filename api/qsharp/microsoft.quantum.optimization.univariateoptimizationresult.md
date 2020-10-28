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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="109fa-102">UnivariateOptimizationResult 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="109fa-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="109fa-103">命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="109fa-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="109fa-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="109fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="109fa-105">表示優化單變數函數的結果。</span><span class="sxs-lookup"><span data-stu-id="109fa-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="109fa-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="109fa-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="109fa-107">座標： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="109fa-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="109fa-108">找到最佳的輸入。</span><span class="sxs-lookup"><span data-stu-id="109fa-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="109fa-109">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="109fa-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="109fa-110">函數所傳回的最理想值。</span><span class="sxs-lookup"><span data-stu-id="109fa-110">Value returned by the function at its optimum.</span></span>