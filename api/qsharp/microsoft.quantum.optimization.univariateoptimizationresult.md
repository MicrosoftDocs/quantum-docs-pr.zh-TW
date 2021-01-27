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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="3d91f-102">UnivariateOptimizationResult 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="3d91f-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="3d91f-103">命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="3d91f-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="3d91f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d91f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d91f-105">表示優化單變數函數的結果。</span><span class="sxs-lookup"><span data-stu-id="3d91f-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="3d91f-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="3d91f-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="3d91f-107">座標： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3d91f-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3d91f-108">找到最佳的輸入。</span><span class="sxs-lookup"><span data-stu-id="3d91f-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="3d91f-109">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3d91f-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3d91f-110">函數所傳回的最理想值。</span><span class="sxs-lookup"><span data-stu-id="3d91f-110">Value returned by the function at its optimum.</span></span>