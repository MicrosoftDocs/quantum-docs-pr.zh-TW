---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699419"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="4e57c-102">SquareArrayFact 函式</span><span class="sxs-lookup"><span data-stu-id="4e57c-102">SquareArrayFact function</span></span>

<span data-ttu-id="4e57c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4e57c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4e57c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e57c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e57c-105">表示二維陣列具有方形形狀的條件</span><span class="sxs-lookup"><span data-stu-id="4e57c-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="4e57c-106">描述</span><span class="sxs-lookup"><span data-stu-id="4e57c-106">Description</span></span>

<span data-ttu-id="4e57c-107">此函式會判斷陣列中的每個資料列都有相同數目的元素，因為陣列中的資料列 (元素) 。</span><span class="sxs-lookup"><span data-stu-id="4e57c-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="4e57c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="4e57c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4e57c-109">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="4e57c-109">array : 'T[][]</span></span>

<span data-ttu-id="4e57c-110">二維元素陣列</span><span class="sxs-lookup"><span data-stu-id="4e57c-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="4e57c-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4e57c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4e57c-112">如果陣列不是正方形陣列，要列印的訊息</span><span class="sxs-lookup"><span data-stu-id="4e57c-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e57c-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e57c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4e57c-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="4e57c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e57c-115">不要</span><span class="sxs-lookup"><span data-stu-id="4e57c-115">'T</span></span>

<span data-ttu-id="4e57c-116">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4e57c-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e57c-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e57c-117">See Also</span></span>

- [<span data-ttu-id="4e57c-118">RectangularArrayFact。</span><span class="sxs-lookup"><span data-stu-id="4e57c-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)