---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699474"
---
# <a name="head-function"></a><span data-ttu-id="a7d7a-102">Head 函數</span><span class="sxs-lookup"><span data-stu-id="a7d7a-102">Head function</span></span>

<span data-ttu-id="a7d7a-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7d7a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7d7a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7d7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7d7a-105">傳回陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="a7d7a-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="a7d7a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a7d7a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a7d7a-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="a7d7a-107">array : 'A[]</span></span>

<span data-ttu-id="a7d7a-108">取得第一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="a7d7a-108">Array of which the first element is taken.</span></span> <span data-ttu-id="a7d7a-109">陣列的長度至少必須為1。</span><span class="sxs-lookup"><span data-stu-id="a7d7a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="a7d7a-110">輸出： ' A</span><span class="sxs-lookup"><span data-stu-id="a7d7a-110">Output : 'A</span></span>

<span data-ttu-id="a7d7a-111">陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="a7d7a-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7d7a-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="a7d7a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a7d7a-113">' A</span><span class="sxs-lookup"><span data-stu-id="a7d7a-113">'A</span></span>

<span data-ttu-id="a7d7a-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="a7d7a-114">The type of the array elements.</span></span>