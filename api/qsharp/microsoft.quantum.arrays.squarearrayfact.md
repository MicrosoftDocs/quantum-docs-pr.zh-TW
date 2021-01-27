---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850970"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="db01f-102">SquareArrayFact 函式</span><span class="sxs-lookup"><span data-stu-id="db01f-102">SquareArrayFact function</span></span>

<span data-ttu-id="db01f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db01f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db01f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db01f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db01f-105">表示二維陣列具有方形形狀的條件</span><span class="sxs-lookup"><span data-stu-id="db01f-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="db01f-106">描述</span><span class="sxs-lookup"><span data-stu-id="db01f-106">Description</span></span>

<span data-ttu-id="db01f-107">此函式會判斷陣列中的每個資料列都有相同數目的元素，因為陣列中的資料列 (元素) 。</span><span class="sxs-lookup"><span data-stu-id="db01f-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="db01f-108">輸入</span><span class="sxs-lookup"><span data-stu-id="db01f-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="db01f-109">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="db01f-109">array : 'T[][]</span></span>

<span data-ttu-id="db01f-110">二維元素陣列</span><span class="sxs-lookup"><span data-stu-id="db01f-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="db01f-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="db01f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="db01f-112">如果陣列不是正方形陣列，要列印的訊息</span><span class="sxs-lookup"><span data-stu-id="db01f-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="db01f-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db01f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db01f-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="db01f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db01f-115">不要</span><span class="sxs-lookup"><span data-stu-id="db01f-115">'T</span></span>

<span data-ttu-id="db01f-116">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="db01f-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="db01f-117">範例</span><span class="sxs-lookup"><span data-stu-id="db01f-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="db01f-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="db01f-118">See Also</span></span>

- [<span data-ttu-id="db01f-119">RectangularArrayFact。</span><span class="sxs-lookup"><span data-stu-id="db01f-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)