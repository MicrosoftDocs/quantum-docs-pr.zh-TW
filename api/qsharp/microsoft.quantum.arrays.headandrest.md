---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848552"
---
# <a name="headandrest-function"></a><span data-ttu-id="a7b8c-102">HeadAndRest 函式</span><span class="sxs-lookup"><span data-stu-id="a7b8c-102">HeadAndRest function</span></span>

<span data-ttu-id="a7b8c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7b8c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7b8c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7b8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7b8c-105">傳回陣列的第一個和所有其餘元素的元組。</span><span class="sxs-lookup"><span data-stu-id="a7b8c-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="a7b8c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a7b8c-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a7b8c-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="a7b8c-107">array : 'A[]</span></span>

<span data-ttu-id="a7b8c-108">至少有一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="a7b8c-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a7b8c-109">輸出： ( ' A，' A [] ) </span><span class="sxs-lookup"><span data-stu-id="a7b8c-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="a7b8c-110">陣列的第一個和所有其餘元素的元組。</span><span class="sxs-lookup"><span data-stu-id="a7b8c-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7b8c-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="a7b8c-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a7b8c-112">' A</span><span class="sxs-lookup"><span data-stu-id="a7b8c-112">'A</span></span>

<span data-ttu-id="a7b8c-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="a7b8c-113">The type of the array elements.</span></span>