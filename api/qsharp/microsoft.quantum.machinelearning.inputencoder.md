---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211741"
---
# <a name="inputencoder-function"></a><span data-ttu-id="9ebfc-102">InputEncoder 函式</span><span class="sxs-lookup"><span data-stu-id="9ebfc-102">InputEncoder function</span></span>

<span data-ttu-id="9ebfc-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9ebfc-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9ebfc-105">如果有一組係數和容錯，則會傳回狀態準備作業，將每個係數準備為計算基礎狀態的對應波幅。</span><span class="sxs-lookup"><span data-stu-id="9ebfc-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="9ebfc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9ebfc-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="9ebfc-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9ebfc-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9ebfc-108">要編碼為輸入狀態的係數。</span><span class="sxs-lookup"><span data-stu-id="9ebfc-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="9ebfc-109">輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="9ebfc-110">一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="9ebfc-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>