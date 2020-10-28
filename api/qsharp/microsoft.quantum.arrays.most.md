---
uid: Microsoft.Quantum.Arrays.Most
title: 最多功能
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699443"
---
# <a name="most-function"></a><span data-ttu-id="b552e-102">最多功能</span><span class="sxs-lookup"><span data-stu-id="b552e-102">Most function</span></span>

<span data-ttu-id="b552e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b552e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b552e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b552e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b552e-105">建立等於輸入陣列的陣列，但最後一個陣列元素已卸載。</span><span class="sxs-lookup"><span data-stu-id="b552e-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b552e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b552e-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b552e-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="b552e-107">array : 'T[]</span></span>

<span data-ttu-id="b552e-108">陣列，其優先于倒數第二個元素，以形成輸出陣列。</span><span class="sxs-lookup"><span data-stu-id="b552e-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b552e-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="b552e-109">Output : 'T[]</span></span>

<span data-ttu-id="b552e-110">包含元素的陣列 `array[0..Length(array) - 2]` 。</span><span class="sxs-lookup"><span data-stu-id="b552e-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b552e-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="b552e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b552e-112">不要</span><span class="sxs-lookup"><span data-stu-id="b552e-112">'T</span></span>

<span data-ttu-id="b552e-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="b552e-113">The type of the array elements.</span></span>