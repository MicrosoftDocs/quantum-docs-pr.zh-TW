---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220411"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="0a2eb-102">RectangularArrayFact 函式</span><span class="sxs-lookup"><span data-stu-id="0a2eb-102">RectangularArrayFact function</span></span>

<span data-ttu-id="0a2eb-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0a2eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0a2eb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a2eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a2eb-105">表示二維陣列具有矩形形狀的條件</span><span class="sxs-lookup"><span data-stu-id="0a2eb-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="0a2eb-106">描述</span><span class="sxs-lookup"><span data-stu-id="0a2eb-106">Description</span></span>

<span data-ttu-id="0a2eb-107">此函式會判斷陣列中的每個資料列都具有相同的長度。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="0a2eb-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0a2eb-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="0a2eb-109">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="0a2eb-109">array : 'T[][]</span></span>

<span data-ttu-id="0a2eb-110">二維元素陣列</span><span class="sxs-lookup"><span data-stu-id="0a2eb-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="0a2eb-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0a2eb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0a2eb-112">如果陣列不是矩形陣列，要列印的訊息</span><span class="sxs-lookup"><span data-stu-id="0a2eb-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a2eb-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a2eb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0a2eb-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="0a2eb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a2eb-115">不要</span><span class="sxs-lookup"><span data-stu-id="0a2eb-115">'T</span></span>

<span data-ttu-id="0a2eb-116">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a2eb-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0a2eb-117">See Also</span></span>

- [<span data-ttu-id="0a2eb-118">SquareArrayFact。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)