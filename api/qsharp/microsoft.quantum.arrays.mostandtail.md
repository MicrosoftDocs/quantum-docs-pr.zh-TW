---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220564"
---
# <a name="mostandtail-function"></a><span data-ttu-id="59e2e-102">MostAndTail 函式</span><span class="sxs-lookup"><span data-stu-id="59e2e-102">MostAndTail function</span></span>

<span data-ttu-id="59e2e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="59e2e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="59e2e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59e2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59e2e-105">傳回陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="59e2e-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="59e2e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="59e2e-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="59e2e-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="59e2e-107">array : 'A[]</span></span>

<span data-ttu-id="59e2e-108">至少有一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="59e2e-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="59e2e-109">輸出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="59e2e-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="59e2e-110">陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="59e2e-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="59e2e-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="59e2e-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="59e2e-112">' A</span><span class="sxs-lookup"><span data-stu-id="59e2e-112">'A</span></span>

<span data-ttu-id="59e2e-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="59e2e-113">The type of the array elements.</span></span>