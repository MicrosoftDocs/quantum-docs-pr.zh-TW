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
# <a name="localunivariateminimum-function"></a><span data-ttu-id="25c08-102">LocalUnivariateMinimum 函式</span><span class="sxs-lookup"><span data-stu-id="25c08-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="25c08-103">命名空間： [Microsoft 量子. 優化](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="25c08-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="25c08-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25c08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25c08-105">使用黃金間隔搜尋，傳回單變數函式在限定間隔上的最小值。</span><span class="sxs-lookup"><span data-stu-id="25c08-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="25c08-106">輸入</span><span class="sxs-lookup"><span data-stu-id="25c08-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="25c08-107">fn： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25c08-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25c08-108">要最小化的單變數函數。</span><span class="sxs-lookup"><span data-stu-id="25c08-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="25c08-109">界限： ([雙精度](xref:microsoft.quantum.lang-ref.double)浮[點數](xref:microsoft.quantum.lang-ref.double)) </span><span class="sxs-lookup"><span data-stu-id="25c08-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="25c08-110">要尋找區域最小值的間隔。</span><span class="sxs-lookup"><span data-stu-id="25c08-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="25c08-111">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25c08-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25c08-112">函數輸入中要容許的精確度。</span><span class="sxs-lookup"><span data-stu-id="25c08-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="25c08-113">搜尋本機 optima 將會繼續進行，直到間隔小於此容錯的寬度為止。</span><span class="sxs-lookup"><span data-stu-id="25c08-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="25c08-114">輸出： [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="25c08-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="25c08-115">指定之函式的本機 optima，位於指定的範圍內。</span><span class="sxs-lookup"><span data-stu-id="25c08-115">A local optima of the given function, located within the given bounds.</span></span>