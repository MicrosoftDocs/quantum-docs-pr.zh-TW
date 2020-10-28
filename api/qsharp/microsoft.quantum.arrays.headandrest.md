---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699473"
---
# <a name="headandrest-function"></a><span data-ttu-id="c7e84-102">HeadAndRest 函式</span><span class="sxs-lookup"><span data-stu-id="c7e84-102">HeadAndRest function</span></span>

<span data-ttu-id="c7e84-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c7e84-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c7e84-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7e84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7e84-105">傳回陣列的第一個和所有其餘元素的元組。</span><span class="sxs-lookup"><span data-stu-id="c7e84-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="c7e84-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c7e84-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="c7e84-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="c7e84-107">array : 'A[]</span></span>

<span data-ttu-id="c7e84-108">至少有一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="c7e84-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="c7e84-109">輸出： ( ' A，' A [] ) </span><span class="sxs-lookup"><span data-stu-id="c7e84-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="c7e84-110">陣列的第一個和所有其餘元素的元組。</span><span class="sxs-lookup"><span data-stu-id="c7e84-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c7e84-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="c7e84-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="c7e84-112">' A</span><span class="sxs-lookup"><span data-stu-id="c7e84-112">'A</span></span>

<span data-ttu-id="c7e84-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="c7e84-113">The type of the array elements.</span></span>