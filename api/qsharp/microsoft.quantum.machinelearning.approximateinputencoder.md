---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 2e39318cfaf3321c33b08f742bb25a9276b7e660
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196594"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="7a944-102">ApproximateInputEncoder 函式</span><span class="sxs-lookup"><span data-stu-id="7a944-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="7a944-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7a944-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7a944-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7a944-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7a944-105">假設有一組係數和容錯，則會傳回狀態準備作業，以將每個係數準備為計算基礎狀態的對應波幅，最多可達指定的容錯。</span><span class="sxs-lookup"><span data-stu-id="7a944-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="7a944-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7a944-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="7a944-107">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7a944-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7a944-108">用來將指定係數編碼成輸入狀態的近似值誤差。</span><span class="sxs-lookup"><span data-stu-id="7a944-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="7a944-109">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7a944-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7a944-110">要編碼為輸入狀態的係數。</span><span class="sxs-lookup"><span data-stu-id="7a944-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="7a944-111">輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="7a944-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="7a944-112">一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="7a944-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>