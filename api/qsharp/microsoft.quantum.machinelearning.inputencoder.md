---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852948"
---
# <a name="inputencoder-function"></a><span data-ttu-id="b3818-102">InputEncoder 函式</span><span class="sxs-lookup"><span data-stu-id="b3818-102">InputEncoder function</span></span>

<span data-ttu-id="b3818-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3818-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b3818-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3818-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b3818-105">如果有一組係數和容錯，則會傳回狀態準備作業，將每個係數準備為計算基礎狀態的對應波幅。</span><span class="sxs-lookup"><span data-stu-id="b3818-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="b3818-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b3818-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="b3818-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b3818-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b3818-108">要編碼為輸入狀態的係數。</span><span class="sxs-lookup"><span data-stu-id="b3818-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="b3818-109">輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="b3818-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="b3818-110">一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="b3818-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>