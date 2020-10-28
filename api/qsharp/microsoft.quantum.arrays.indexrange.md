---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699468"
---
# <a name="indexrange-function"></a><span data-ttu-id="b6b8f-102">IndexRange 函式</span><span class="sxs-lookup"><span data-stu-id="b6b8f-102">IndexRange function</span></span>

<span data-ttu-id="b6b8f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b6b8f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b6b8f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6b8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6b8f-105">指定陣列時，會傳回該陣列的索引範圍，適用于 for 迴圈。</span><span class="sxs-lookup"><span data-stu-id="b6b8f-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="b6b8f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b6b8f-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="b6b8f-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="b6b8f-107">array : 'TElement[]</span></span>

<span data-ttu-id="b6b8f-108">應傳回其索引範圍的陣列。</span><span class="sxs-lookup"><span data-stu-id="b6b8f-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="b6b8f-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b6b8f-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="b6b8f-110">陣列所有索引的範圍。</span><span class="sxs-lookup"><span data-stu-id="b6b8f-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b6b8f-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="b6b8f-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="b6b8f-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="b6b8f-112">'TElement</span></span>

<span data-ttu-id="b6b8f-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="b6b8f-113">The type of elements of the array.</span></span>