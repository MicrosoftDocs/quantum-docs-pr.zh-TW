---
uid: Microsoft.Quantum.Arrays.ElementAt
title: Parameters.alternatefilters.elementat 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842810"
---
# <a name="elementat-function"></a><span data-ttu-id="21d11-102">Parameters.alternatefilters.elementat 函式</span><span class="sxs-lookup"><span data-stu-id="21d11-102">ElementAt function</span></span>

<span data-ttu-id="21d11-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21d11-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21d11-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21d11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21d11-105">傳回位於陣列中指定索引處的。</span><span class="sxs-lookup"><span data-stu-id="21d11-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="21d11-106">輸入</span><span class="sxs-lookup"><span data-stu-id="21d11-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="21d11-107">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21d11-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21d11-108">元素的索引</span><span class="sxs-lookup"><span data-stu-id="21d11-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="21d11-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="21d11-109">array : 'T[]</span></span>

<span data-ttu-id="21d11-110">要編制索引的陣列。</span><span class="sxs-lookup"><span data-stu-id="21d11-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="21d11-111">輸出： t</span><span class="sxs-lookup"><span data-stu-id="21d11-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="21d11-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="21d11-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21d11-113">不要</span><span class="sxs-lookup"><span data-stu-id="21d11-113">'T</span></span>

<span data-ttu-id="21d11-114">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="21d11-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="21d11-115">範例</span><span class="sxs-lookup"><span data-stu-id="21d11-115">Example</span></span>

<span data-ttu-id="21d11-116">取得四個知名整數序列中的第三個數字。</span><span class="sxs-lookup"><span data-stu-id="21d11-116">Get the third number in four famous integer sequences.</span></span> <span data-ttu-id="21d11-117"> (請注意，0索引會對應到序列的 _第一個_ 值。 ) </span><span class="sxs-lookup"><span data-stu-id="21d11-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a><span data-ttu-id="21d11-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21d11-118">See Also</span></span>

- [<span data-ttu-id="21d11-119">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="21d11-119">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="21d11-120">ElementsAt。</span><span class="sxs-lookup"><span data-stu-id="21d11-120">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)