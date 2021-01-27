---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845788"
---
# <a name="indexrange-function"></a><span data-ttu-id="b59f4-102">IndexRange 函式</span><span class="sxs-lookup"><span data-stu-id="b59f4-102">IndexRange function</span></span>

<span data-ttu-id="b59f4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b59f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b59f4-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b59f4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b59f4-105">指定陣列時，會傳回該陣列的索引範圍，適用于 for 迴圈。</span><span class="sxs-lookup"><span data-stu-id="b59f4-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="b59f4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b59f4-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="b59f4-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="b59f4-107">array : 'TElement[]</span></span>

<span data-ttu-id="b59f4-108">應傳回其索引範圍的陣列。</span><span class="sxs-lookup"><span data-stu-id="b59f4-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="b59f4-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b59f4-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="b59f4-110">陣列所有索引的範圍。</span><span class="sxs-lookup"><span data-stu-id="b59f4-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b59f4-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="b59f4-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="b59f4-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="b59f4-112">'TElement</span></span>

<span data-ttu-id="b59f4-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="b59f4-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="b59f4-114">範例</span><span class="sxs-lookup"><span data-stu-id="b59f4-114">Example</span></span>

<span data-ttu-id="b59f4-115">下列 `for` 迴圈是相等的：</span><span class="sxs-lookup"><span data-stu-id="b59f4-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```