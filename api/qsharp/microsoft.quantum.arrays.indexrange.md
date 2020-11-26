---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220938"
---
# <a name="indexrange-function"></a><span data-ttu-id="d1308-102">IndexRange 函式</span><span class="sxs-lookup"><span data-stu-id="d1308-102">IndexRange function</span></span>

<span data-ttu-id="d1308-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d1308-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d1308-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d1308-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d1308-105">指定陣列時，會傳回該陣列的索引範圍，適用于 for 迴圈。</span><span class="sxs-lookup"><span data-stu-id="d1308-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="d1308-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d1308-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="d1308-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="d1308-107">array : 'TElement[]</span></span>

<span data-ttu-id="d1308-108">應傳回其索引範圍的陣列。</span><span class="sxs-lookup"><span data-stu-id="d1308-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="d1308-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d1308-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d1308-110">陣列所有索引的範圍。</span><span class="sxs-lookup"><span data-stu-id="d1308-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d1308-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="d1308-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="d1308-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="d1308-112">'TElement</span></span>

<span data-ttu-id="d1308-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="d1308-113">The type of elements of the array.</span></span>