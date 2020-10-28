---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列舉函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699494"
---
# <a name="enumerated-function"></a><span data-ttu-id="c15cc-102">列舉函數</span><span class="sxs-lookup"><span data-stu-id="c15cc-102">Enumerated function</span></span>

<span data-ttu-id="c15cc-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c15cc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c15cc-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c15cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c15cc-105">指定陣列時，會傳回新的陣列，其中包含原始陣列的元素以及每個專案的索引。</span><span class="sxs-lookup"><span data-stu-id="c15cc-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="c15cc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c15cc-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="c15cc-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="c15cc-107">array : 'TElement[]</span></span>

<span data-ttu-id="c15cc-108">要列舉其元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="c15cc-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="c15cc-109">輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="c15cc-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="c15cc-110">新的陣列，其中包含原始陣列的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="c15cc-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c15cc-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="c15cc-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="c15cc-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="c15cc-112">'TElement</span></span>

<span data-ttu-id="c15cc-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="c15cc-113">The type of elements of the array.</span></span>