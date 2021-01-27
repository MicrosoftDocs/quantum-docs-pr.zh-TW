---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 295aa4e2d79857405186b835d9788f59db83d1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842800"
---
# <a name="elementsat-function"></a><span data-ttu-id="66c14-102">ElementsAt 函式</span><span class="sxs-lookup"><span data-stu-id="66c14-102">ElementsAt function</span></span>

<span data-ttu-id="66c14-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="66c14-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="66c14-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66c14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66c14-105">傳回指定之索引範圍的陣列元素。</span><span class="sxs-lookup"><span data-stu-id="66c14-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="66c14-106">輸入</span><span class="sxs-lookup"><span data-stu-id="66c14-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="66c14-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="66c14-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="66c14-108">陣列索引的範圍</span><span class="sxs-lookup"><span data-stu-id="66c14-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="66c14-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="66c14-109">array : 'T[]</span></span>

<span data-ttu-id="66c14-110">Array</span><span class="sxs-lookup"><span data-stu-id="66c14-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="66c14-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="66c14-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66c14-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="66c14-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66c14-113">不要</span><span class="sxs-lookup"><span data-stu-id="66c14-113">'T</span></span>

<span data-ttu-id="66c14-114">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="66c14-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="66c14-115">範例</span><span class="sxs-lookup"><span data-stu-id="66c14-115">Example</span></span>

<span data-ttu-id="66c14-116">取得著名整數序列中的奇數索引。</span><span class="sxs-lookup"><span data-stu-id="66c14-116">Get the odd indexes in famous integer sequences.</span></span> <span data-ttu-id="66c14-117"> (請注意，0索引會對應到序列的 _第一個_ 值。 ) </span><span class="sxs-lookup"><span data-stu-id="66c14-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famousOdd = Mapped(ElementsAt<Int>(0..2..9, _), [lucas, prime, fibonacci, catalan]);
// same as: famousOdd = [[2, 3, 7, 18, 47], [2, 5, 11, 17, 23], [0, 1, 3, 8, 21], [1, 2, 14, 132, 1430]]
```

## <a name="see-also"></a><span data-ttu-id="66c14-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66c14-118">See Also</span></span>

- [<span data-ttu-id="66c14-119">Parameters.alternatefilters.elementat。</span><span class="sxs-lookup"><span data-stu-id="66c14-119">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="66c14-120">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="66c14-120">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)