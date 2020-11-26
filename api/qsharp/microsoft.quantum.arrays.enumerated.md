---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列舉函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221414"
---
# <a name="enumerated-function"></a><span data-ttu-id="a1a39-102">列舉函數</span><span class="sxs-lookup"><span data-stu-id="a1a39-102">Enumerated function</span></span>

<span data-ttu-id="a1a39-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a1a39-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a1a39-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1a39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1a39-105">指定陣列時，會傳回新的陣列，其中包含原始陣列的元素以及每個專案的索引。</span><span class="sxs-lookup"><span data-stu-id="a1a39-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="a1a39-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a1a39-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="a1a39-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="a1a39-107">array : 'TElement[]</span></span>

<span data-ttu-id="a1a39-108">要列舉其元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="a1a39-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="a1a39-109">輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="a1a39-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="a1a39-110">新的陣列，其中包含原始陣列的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="a1a39-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a1a39-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="a1a39-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="a1a39-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="a1a39-112">'TElement</span></span>

<span data-ttu-id="a1a39-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="a1a39-113">The type of elements of the array.</span></span>