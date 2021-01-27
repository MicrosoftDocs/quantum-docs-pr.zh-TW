---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列舉函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848133"
---
# <a name="enumerated-function"></a><span data-ttu-id="3e20d-102">列舉函數</span><span class="sxs-lookup"><span data-stu-id="3e20d-102">Enumerated function</span></span>

<span data-ttu-id="3e20d-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3e20d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3e20d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e20d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e20d-105">指定陣列時，會傳回新的陣列，其中包含原始陣列的元素以及每個專案的索引。</span><span class="sxs-lookup"><span data-stu-id="3e20d-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="3e20d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3e20d-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="3e20d-107">陣列： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="3e20d-107">array : 'TElement[]</span></span>

<span data-ttu-id="3e20d-108">要列舉其元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="3e20d-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="3e20d-109">輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="3e20d-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="3e20d-110">新的陣列，其中包含原始陣列的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="3e20d-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3e20d-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="3e20d-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="3e20d-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="3e20d-112">'TElement</span></span>

<span data-ttu-id="3e20d-113">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="3e20d-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="3e20d-114">範例</span><span class="sxs-lookup"><span data-stu-id="3e20d-114">Example</span></span>

<span data-ttu-id="3e20d-115">下列 `for` 迴圈是相等的：</span><span class="sxs-lookup"><span data-stu-id="3e20d-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```