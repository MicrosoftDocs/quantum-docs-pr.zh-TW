---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845594"
---
# <a name="mostandtail-function"></a><span data-ttu-id="a2d84-102">MostAndTail 函式</span><span class="sxs-lookup"><span data-stu-id="a2d84-102">MostAndTail function</span></span>

<span data-ttu-id="a2d84-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a2d84-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a2d84-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2d84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2d84-105">傳回陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="a2d84-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="a2d84-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a2d84-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a2d84-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="a2d84-107">array : 'A[]</span></span>

<span data-ttu-id="a2d84-108">至少有一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="a2d84-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a2d84-109">輸出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="a2d84-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="a2d84-110">陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="a2d84-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a2d84-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="a2d84-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a2d84-112">' A</span><span class="sxs-lookup"><span data-stu-id="a2d84-112">'A</span></span>

<span data-ttu-id="a2d84-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="a2d84-113">The type of the array elements.</span></span>