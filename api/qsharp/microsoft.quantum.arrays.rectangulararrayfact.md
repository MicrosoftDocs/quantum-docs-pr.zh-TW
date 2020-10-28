---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699430"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="49e39-102">RectangularArrayFact 函式</span><span class="sxs-lookup"><span data-stu-id="49e39-102">RectangularArrayFact function</span></span>

<span data-ttu-id="49e39-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="49e39-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="49e39-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49e39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49e39-105">表示二維陣列具有矩形形狀的條件</span><span class="sxs-lookup"><span data-stu-id="49e39-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="49e39-106">描述</span><span class="sxs-lookup"><span data-stu-id="49e39-106">Description</span></span>

<span data-ttu-id="49e39-107">此函式會判斷陣列中的每個資料列都具有相同的長度。</span><span class="sxs-lookup"><span data-stu-id="49e39-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="49e39-108">輸入</span><span class="sxs-lookup"><span data-stu-id="49e39-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="49e39-109">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="49e39-109">array : 'T[][]</span></span>

<span data-ttu-id="49e39-110">二維元素陣列</span><span class="sxs-lookup"><span data-stu-id="49e39-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="49e39-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="49e39-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="49e39-112">如果陣列不是矩形陣列，要列印的訊息</span><span class="sxs-lookup"><span data-stu-id="49e39-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="49e39-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49e39-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="49e39-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="49e39-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49e39-115">不要</span><span class="sxs-lookup"><span data-stu-id="49e39-115">'T</span></span>

<span data-ttu-id="49e39-116">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="49e39-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="49e39-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="49e39-117">See Also</span></span>

- [<span data-ttu-id="49e39-118">SquareArrayFact。</span><span class="sxs-lookup"><span data-stu-id="49e39-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)