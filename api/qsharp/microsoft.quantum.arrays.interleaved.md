---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交錯函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848104"
---
# <a name="interleaved-function"></a><span data-ttu-id="6fb8e-102">交錯函式</span><span class="sxs-lookup"><span data-stu-id="6fb8e-102">Interleaved function</span></span>

<span data-ttu-id="6fb8e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6fb8e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6fb8e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fb8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fb8e-105">交錯 (的兩個數組幾乎) 相同大小。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="6fb8e-106">描述</span><span class="sxs-lookup"><span data-stu-id="6fb8e-106">Description</span></span>

<span data-ttu-id="6fb8e-107">此函式會傳回兩個數組的交錯，從第一個陣列中的第一個元素開始，然後是第二個數組中的第一個元素，依此類推。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="6fb8e-108">第一個陣列的長度必須與第二個數組的長度相同，或者可以有一個以上的元素。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="6fb8e-109">輸入</span><span class="sxs-lookup"><span data-stu-id="6fb8e-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="6fb8e-110">first： t []</span><span class="sxs-lookup"><span data-stu-id="6fb8e-110">first : 'T[]</span></span>

<span data-ttu-id="6fb8e-111">要交錯的第一個陣列。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="6fb8e-112">second： t []</span><span class="sxs-lookup"><span data-stu-id="6fb8e-112">second : 'T[]</span></span>

<span data-ttu-id="6fb8e-113">要交錯的第二個數組。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="6fb8e-114">Output： t []</span><span class="sxs-lookup"><span data-stu-id="6fb8e-114">Output : 'T[]</span></span>

<span data-ttu-id="6fb8e-115">交錯陣列</span><span class="sxs-lookup"><span data-stu-id="6fb8e-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6fb8e-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="6fb8e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6fb8e-117">不要</span><span class="sxs-lookup"><span data-stu-id="6fb8e-117">'T</span></span>

<span data-ttu-id="6fb8e-118">和之每個元素的型別 `first` `second` 。</span><span class="sxs-lookup"><span data-stu-id="6fb8e-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="6fb8e-119">範例</span><span class="sxs-lookup"><span data-stu-id="6fb8e-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```