---
uid: Microsoft.Quantum.Arrays.Where
title: Where 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219918"
---
# <a name="where-function"></a><span data-ttu-id="e2d8b-102">Where 函數</span><span class="sxs-lookup"><span data-stu-id="e2d8b-102">Where function</span></span>

<span data-ttu-id="e2d8b-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e2d8b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e2d8b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2d8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2d8b-105">假設有述詞和陣列，則會傳回該陣列的索引，其述詞為 true。</span><span class="sxs-lookup"><span data-stu-id="e2d8b-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="e2d8b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e2d8b-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e2d8b-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e2d8b-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e2d8b-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="e2d8b-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="e2d8b-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="e2d8b-109">array : 'T[]</span></span>

<span data-ttu-id="e2d8b-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="e2d8b-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e2d8b-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e2d8b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e2d8b-112">索引的陣列，其中 `predicate` 為 true。</span><span class="sxs-lookup"><span data-stu-id="e2d8b-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e2d8b-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="e2d8b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2d8b-114">不要</span><span class="sxs-lookup"><span data-stu-id="e2d8b-114">'T</span></span>

<span data-ttu-id="e2d8b-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="e2d8b-115">The type of `array` elements.</span></span>