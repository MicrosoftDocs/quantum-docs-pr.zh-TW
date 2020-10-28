---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697231"
---
# <a name="inputencoder-function"></a><span data-ttu-id="19a2d-102">InputEncoder 函式</span><span class="sxs-lookup"><span data-stu-id="19a2d-102">InputEncoder function</span></span>

<span data-ttu-id="19a2d-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="19a2d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="19a2d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19a2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19a2d-105">如果有一組係數和容錯，則會傳回狀態準備作業，將每個係數準備為計算基礎狀態的對應波幅。</span><span class="sxs-lookup"><span data-stu-id="19a2d-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="19a2d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="19a2d-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="19a2d-107">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="19a2d-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="19a2d-108">要編碼為輸入狀態的係數。</span><span class="sxs-lookup"><span data-stu-id="19a2d-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="19a2d-109">輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="19a2d-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="19a2d-110">一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="19a2d-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>