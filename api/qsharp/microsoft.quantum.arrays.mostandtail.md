---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699442"
---
# <a name="mostandtail-function"></a><span data-ttu-id="f0f44-102">MostAndTail 函式</span><span class="sxs-lookup"><span data-stu-id="f0f44-102">MostAndTail function</span></span>

<span data-ttu-id="f0f44-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0f44-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0f44-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0f44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0f44-105">傳回陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="f0f44-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="f0f44-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f0f44-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="f0f44-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="f0f44-107">array : 'A[]</span></span>

<span data-ttu-id="f0f44-108">至少有一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="f0f44-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="f0f44-109">輸出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="f0f44-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="f0f44-110">陣列中除了一個和最後一個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="f0f44-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0f44-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="f0f44-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="f0f44-112">' A</span><span class="sxs-lookup"><span data-stu-id="f0f44-112">'A</span></span>

<span data-ttu-id="f0f44-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="f0f44-113">The type of the array elements.</span></span>