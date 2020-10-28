---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交錯函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699467"
---
# <a name="interleaved-function"></a><span data-ttu-id="fba89-102">交錯函式</span><span class="sxs-lookup"><span data-stu-id="fba89-102">Interleaved function</span></span>

<span data-ttu-id="fba89-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fba89-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fba89-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fba89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fba89-105">交錯 (的兩個數組幾乎) 相同大小。</span><span class="sxs-lookup"><span data-stu-id="fba89-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="fba89-106">描述</span><span class="sxs-lookup"><span data-stu-id="fba89-106">Description</span></span>

<span data-ttu-id="fba89-107">此函式會傳回兩個數組的交錯，從第一個陣列中的第一個元素開始，然後是第二個數組中的第一個元素，依此類推。</span><span class="sxs-lookup"><span data-stu-id="fba89-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="fba89-108">第一個陣列的長度必須與第二個數組的長度相同，或者可以有一個以上的元素。</span><span class="sxs-lookup"><span data-stu-id="fba89-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="fba89-109">輸入</span><span class="sxs-lookup"><span data-stu-id="fba89-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="fba89-110">first： t []</span><span class="sxs-lookup"><span data-stu-id="fba89-110">first : 'T[]</span></span>

<span data-ttu-id="fba89-111">要交錯的第一個陣列。</span><span class="sxs-lookup"><span data-stu-id="fba89-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="fba89-112">second： t []</span><span class="sxs-lookup"><span data-stu-id="fba89-112">second : 'T[]</span></span>

<span data-ttu-id="fba89-113">要交錯的第二個數組。</span><span class="sxs-lookup"><span data-stu-id="fba89-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="fba89-114">Output： t []</span><span class="sxs-lookup"><span data-stu-id="fba89-114">Output : 'T[]</span></span>

<span data-ttu-id="fba89-115">交錯陣列</span><span class="sxs-lookup"><span data-stu-id="fba89-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fba89-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="fba89-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fba89-117">不要</span><span class="sxs-lookup"><span data-stu-id="fba89-117">'T</span></span>

<span data-ttu-id="fba89-118">和之每個元素的型別 `first` `second` 。</span><span class="sxs-lookup"><span data-stu-id="fba89-118">The type of each element of `first` and `second`.</span></span>