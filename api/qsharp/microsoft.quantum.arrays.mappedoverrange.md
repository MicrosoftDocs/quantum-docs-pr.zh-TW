---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845644"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="8bbce-102">MappedOverRange 函式</span><span class="sxs-lookup"><span data-stu-id="8bbce-102">MappedOverRange function</span></span>

<span data-ttu-id="8bbce-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8bbce-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8bbce-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8bbce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8bbce-105">假設範圍和採用整數做為輸入的函式，則會傳回新的陣列，其中包含函式下範圍值的影像。</span><span class="sxs-lookup"><span data-stu-id="8bbce-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8bbce-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8bbce-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="8bbce-107">對應工具： [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="8bbce-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="8bbce-108">中 `Int` `'T` 用來對應範圍值的函式。</span><span class="sxs-lookup"><span data-stu-id="8bbce-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="8bbce-109">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8bbce-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8bbce-110">整數的範圍。</span><span class="sxs-lookup"><span data-stu-id="8bbce-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="8bbce-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="8bbce-111">Output : 'T[]</span></span>

<span data-ttu-id="8bbce-112">由函式 `'T[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="8bbce-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8bbce-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="8bbce-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8bbce-114">不要</span><span class="sxs-lookup"><span data-stu-id="8bbce-114">'T</span></span>

<span data-ttu-id="8bbce-115">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="8bbce-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="8bbce-116">範例</span><span class="sxs-lookup"><span data-stu-id="8bbce-116">Example</span></span>

<span data-ttu-id="8bbce-117">此範例會將1新增至偶數範圍的偶數：</span><span class="sxs-lookup"><span data-stu-id="8bbce-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="8bbce-118">備註</span><span class="sxs-lookup"><span data-stu-id="8bbce-118">Remarks</span></span>

<span data-ttu-id="8bbce-119">函數是針對泛型型別定義的，也就是說，每當我們有函式時， `mapper: Int -> 'T` 我們可以對應範圍的值，並產生型別的陣列 `'T[]` 。</span><span class="sxs-lookup"><span data-stu-id="8bbce-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bbce-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8bbce-120">See Also</span></span>

- [<span data-ttu-id="8bbce-121">。對應的</span><span class="sxs-lookup"><span data-stu-id="8bbce-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)