---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699413"
---
# <a name="tail-function"></a><span data-ttu-id="4a8da-102">Tail 函數</span><span class="sxs-lookup"><span data-stu-id="4a8da-102">Tail function</span></span>

<span data-ttu-id="4a8da-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a8da-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a8da-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a8da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a8da-105">傳回陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="4a8da-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="4a8da-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4a8da-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="4a8da-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="4a8da-107">array : 'A[]</span></span>

<span data-ttu-id="4a8da-108">取得最後一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="4a8da-108">Array of which the last element is taken.</span></span> <span data-ttu-id="4a8da-109">陣列的長度至少必須為1。</span><span class="sxs-lookup"><span data-stu-id="4a8da-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="4a8da-110">輸出： ' A</span><span class="sxs-lookup"><span data-stu-id="4a8da-110">Output : 'A</span></span>

<span data-ttu-id="4a8da-111">陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="4a8da-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a8da-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="4a8da-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="4a8da-113">' A</span><span class="sxs-lookup"><span data-stu-id="4a8da-113">'A</span></span>

<span data-ttu-id="4a8da-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="4a8da-114">The type of the array elements.</span></span>